<template>
  <v-main>
    <v-row align-content="center" justify="center">
      <v-col cols="10" class="ml-12 pl-12 mr-0" align-self="center">
        <h1 v-if="!edit[0].title" style="word-wrap: break-word;">{{ title }}</h1>
        <v-text-field
            v-if="edit[0].title"
            v-model="title"
            label="TITLE"
            outlined
          ></v-text-field>
      </v-col>
      <v-col cols="1">
        <v-btn v-if="!edit[0].title" icon @click="edit[0].title = !edit[0].title">
          <v-icon text>
            mdi-square-edit-outline
          </v-icon>
        </v-btn>
        <v-btn v-if="edit[0].title" text @click="edit[0].title = !edit[0].title">
          SAVE
        </v-btn>
      </v-col>
    </v-row>
    <v-row align-content="center" justify="center">
      <v-col cols="10" align-self="center">
        <v-row class="ml-12" v-for="element in postData" :key="element.id">
          <v-col cols="9" class="ml-12 pl-12">
            <v-textarea
              v-model="postData[element.id-1].elementData.data"
              v-if="element.elementData.type == 'text' && edit[element.id].editable"
              outlined
            />
            <blockquote class="blockquote" v-if="element.elementData.type == 'text' && !edit[element.id].editable">
              {{ postData[element.id-1].elementData.data }}
            </blockquote>
            <v-file-input
              v-if="element.elementData.type == 'img' && edit[element.id].editable"
              v-model="postData[element.id-1].elementData.file"
              accept="image/*"
              color="deep-purple accent-4"
              label="Upload Image"
              placeholder="Upload image ..."
              prepend-icon="mdi-camera"
              outlined
              show-size
            >
              <template v-slot:selection="{ text }">
                <v-chip
                  color="deep-purple accent-4"
                  dark
                  label
                  small
                >
                  {{ text }}
                </v-chip>
              </template>
            </v-file-input>
            <v-text-field
              v-if="element.elementData.type == 'img' && edit[element.id].editable"
              v-model="postData[element.id-1].elementData.alt"
              label="Alternative Text"
              :rules="altTextRules"
              counter="100"
              maxlength="100"
              outlined
              placeholder="Description"
            >
            </v-text-field>
            <img 
              v-if="element.elementData.type == 'img' && !edit[element.id].editable"
              :src="postData[element.id-1].elementData.src"
              :alt="postData[element.id-1].elementData.alt"
              class="post-image"
            />
            <v-file-input
              v-if="element.elementData.type == 'video' && edit[element.id].editable"
              v-model="postData[element.id-1].elementData.file"
              accept="video/*"
              color="deep-purple accent-4"
              label="Upload Image"
              placeholder="Upload video ..."
              prepend-icon="mdi-youtube-play"
              outlined
              show-size
            >
              <template v-slot:selection="{ text }">
                <v-chip
                  color="deep-purple accent-4"
                  dark
                  label
                  small
                >
                  {{ text }}
                </v-chip>
              </template>
            </v-file-input>
            <video 
              v-show="element.elementData.type == 'video' && !edit[element.id].editable"
              :id="'video-'+element.id"
              width="720"
              height="540"
              controls
            >
              <source
                :src="postData[element.id-1].elementData.src"
                type="video/*"
              >
            </video>
            <div v-if="element.elementData.type == 'list'" class="list-div">
              <ol v-if="element.elementData.type == 'list' && element.elementData.ol.status && !edit[element.id].editable">
                <li :v-for="listItem in element.elementData.listItems" :key="listItem">{{listItem}}</li>
              </ol>
              <ul v-if="element.elementData.type == 'list' && element.elementData.ul.status && !edit[element.id].editable">
                <li :v-for="listItem in element.elementData.listItems" :key="listItem">{{listItem}}</li>
              </ul>
            </div>
          </v-col>
          <v-col cols="1">
            <v-btn v-if="!edit[element.id].editable" icon @click="handleEdit(element.id, element.elementData.type)">
              <v-icon text>
                mdi-square-edit-outline
              </v-icon>
            </v-btn>
            <v-btn v-if="edit[element.id].editable" text @click="handleSave(element.id, element.elementData.type)">
              SAVE
            </v-btn>
          </v-col>
          <v-col cols="1">
            <v-btn
              class="mb-2"
              icon
              @click="shiftUp(element.id)"
            >
              <v-icon text>
                mdi-arrow-up-bold
              </v-icon>
            </v-btn>
            <v-btn
              icon
              @click="shiftDown(element.id)"
            >
              <v-icon text>
                mdi-arrow-down-bold
              </v-icon>
            </v-btn>
            <v-btn icon @click="deleteElement(element.id)">
              <v-icon text>
                mdi-delete-forever
              </v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="1" class="ml-12 pl-12 pt-0" align-self="right">
        <v-menu transition="slide-y-transition" bottom offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn style="position: fixed;" small fab v-bind="attrs" v-on="on">
              +
            </v-btn>
          </template>
          <v-list flat>
            <v-btn
              v-for="(item, i) in items"
              :key="i"
              text
              color="brown"
              block
              large
              @click="addElement(item)"
              v-text="item"
            />
          </v-list>
        </v-menu>
      </v-col>
    </v-row>
  </v-main>
</template>
<style scoped>
.post-image{
    width: 700px;
    height: 450px;
}
.list-div {
  border-style: solid;
  border-width:1px;
  border-radius: 4px;
  border-color: rgba(0, 0, 0, 0.38);

}
.list-div::selection {
  background-color: #338FFF;
}
</style>
<script>
export default {
  data: () => ({
    altTextRules: [v => v.length <= 100 || 'Max 100 characters'],
    postData: [],
    items: ["img", "text", "video", "list"],
    edit: [{'title': false},],
    title: "Title Goes HereTitle Goes Here ...Title Goes Here ...Title Goes Here ...Title Goes Here ..."
  }),
  methods: {
    addElement (type) {
      if (this.items.includes(type)) {
        if (type == "text") {
          this.postData.push({
            'id': this.postData.length > 0 ? this.postData.length+1 : 1,
            'elementData' : {
              'type': type,
              'data': 'Hello guys this is fun ...'
            }
          }) 
        }
        else if(type == "img") {
          this.postData.push({
            'id': this.postData.length > 0 ? this.postData.length+1 : 1, 
            'elementData' : {
              'type': type,
              'src': '',
              'alt': '',
              'file': null
            }
          }) 
        }
        else if(type == "video") {
          this.postData.push({
            'id': this.postData.length > 0 ? this.postData.length+1 : 1, 
            'elementData': {
              'type': type,
              'src': '',
              'file': null
            }
          }) 
        }
        else if(type == "list") {
          this.postData.push({
            'id': this.postData.length > 0 ? this.postData.length+1 : 1, 
            'elementData': {
              'type': type,
              'ol': {
                'status': true,
                'type':'digits'
              },
              'ul': {
                'status': false,
                'type': 'disc'
              },
              'listItems': []
            }
          }) 
        }
        this.edit.push({'editable': false})
      }
      else {
        console.error("Invalid! type '" + type + "'")
      }
    },
    shiftDown (id) {
      if (id != this.postData.length) {
        let temp = this.postData[id-1].elementData 
        this.postData[id-1].elementData = this.postData[id].elementData
        this.postData[id].elementData = temp
      }
    },
    shiftUp (id) {
      if (id > 1) {
        let temp = this.postData[id-1].elementData
        this.postData[id-1].elementData = this.postData[id-2].elementData
        this.postData[id-2].elementData = temp
      }
    },
    handleSave (id, type) {
      this.edit[id].editable = !this.edit[id].editable
      console.log(this.postData[id-1].elementData.file)
      console.log(type)
      if(type == "video") {
        this.handleVideoUpload(id);
      }
      else if (type == "img") {
        this.handleImageUpload(id);
      }
    },
    handleEdit (id, type) {
      this.edit[id].editable = !this.edit[id].editable
    },
    deleteElement (id) {
      if(this.postData.length>1 && id != this.postData.length){
        this.postData.splice(id-1, 1)
        this.edit.splice(id, 1)
        for (var i=0; i<this.postData.length; i++) {
          this.postData[i].id = i+1
        }
      }
      else if (id != this.postData.length){
        this.postData.splice(id-1, 1)
        this.edit.splice(id, 1)
      }
      else {
        this.edit.pop()
        this.postData.pop()
      }
    },
    handleImageUpload (id) {
      URL.revokeObjectURL(this.postData[id-1].elementData.src);
      this.postData[id-1].elementData.src =  URL.createObjectURL(this.postData[id-1].elementData.file);
    },
    handleVideoUpload (id) {
      const video = document.getElementById('video-'+id);
      URL.revokeObjectURL(this.postData[id-1].elementData.src);
      video.src = URL.createObjectURL(this.postData[id-1].elementData.file);
      video.play()
      this.postData[id-1].elementData.src =  URL.createObjectURL(this.postData[id-1].elementData.file);
    }
  }
}
</script>
