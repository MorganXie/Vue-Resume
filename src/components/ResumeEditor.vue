<template>
  <div id="resumeEditor">
    <nav>
      <ol >
        <li v-for="(item,index) in resume.config"
            :class="{active:item.field === selected}"
            @click="selected = item.field">
          <svg class="icon">
            <use :xlink:href="`#icon-${item.icon}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="panels">
      <li v-for="item in resume.config" v-show="item.field===selected">
        <div v-if="resume[item.field] instanceof Array">
          <div class="subitme" v-for="subitem in resume[item.field]">
          <div class="resumeField" v-for="(value,key) in subitem">
            <label >{{key}}</label>
            <el-input  class="el-input" :value="value" placeholder="请输入内容"></el-input>
          </div>
        </div>
          <hr>
        </div>
        <div class="resumeField" v-else v-for="(value,key) in resume[item.field]">
          <label> {{key}} </label>
          <el-input  class="el-input" v-model="resume[item.field][key]" placeholder="请输入内容"></el-input>
        </div>
      </li>
    </ol>
  </div>
</template>

<script>
  export default {
    name: 'ResumeEditor',
    data() {
      return {
        selected: 'profile',
        resume: {
          config: [
            {field: 'profile', icon: 'id'},
            {field: 'workHistory', icon: 'work'},
            {field: 'education', icon: 'book'},
            {field: 'projects', icon: 'heart'},
            {field: 'awards', icon: 'cup'},
            {field: 'contacts', icon: 'phone'},
          ],
          profile: {
            name: '',
            city: '',
            selfIntro: ''
          },
          workHistory: [
            {company:'AL',content:'my first job'},
            {company:'TX',content:'my second job'}
          ],
          education: [
            {school:'AL',content:'清华'},
            {school:'AL',content:'北大'}],
          projects: [
            {name:'项目1', content:'123'},
            {name:'项目2', content:'345'}],
          awards: [
            {name:'奖项1',content:'234'},
            {name:'奖项2',content:'345'},
          ],
          contacts: [
            {phone:'123123123'},
            {qq:'12312311231231'},
            {wechat:'12312311231231'}
          ],
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  #resumeEditor {
    background: #ffffff;
    box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.25);
    display: flex;
    flex-direction: row;
    overflow: auto;
    > nav {
      width: 80px;
      background: black;
      color: white;
      > ol {
        > li {
          height: 48px;
          display: flex;
          justify-content: center;
          align-items: center;
          margin-top: 16px;
          margin-bottom: 16px;
          &.active {
            background: white;
            color: black;
          }
        }
      }
    }
    > .panels {
      flex-grow: 1;
      > li {
        padding: 24px;
      }
    }

    svg.icon {
      width: 24px;
      height: 24px;
    }
  }

  ol {
    list-style: none;
  }

  .resumeField {
    > label {
      display: block;
    }
     .el-input {
      margin: 16px 0;
      width: 100%;
      height: 40px;
    }
  }
  hr{
    border:none;
    border-top:1px solid #ddd;
    margin:24px 0;
  }


</style>
