<template>
  <div class="page">
    <header>
      <Topbar></Topbar>
    </header>
    <main>
      <ResumeEditor></ResumeEditor>
      <ResumePreview></ResumePreview>
    </main>
  </div>
</template>

<script>
  import 'normalize.css/normalize.css'
  import './assets/reset.css'
  import Topbar from './components/Topbar.vue'
  import ResumeEditor from './components/ResumeEditor.vue'
  import ResumePreview from './components/ResumePreview.vue'


  export default {
    name: 'app',
    data() {
      return {
        text: 'xiexuan'
      }
    },
    components: {
      Topbar, ResumeEditor, ResumePreview
    }
  }
</script>

<style>
  .page {
    height: 100vh;
    display: flex;
    flex-direction: column;
    background: #EAEBEC;
  }

  .page > main {
    min-width: 1024px;
    max-width: 1440px;
    margin-top: 16px;
    margin-bottom: 16px;
    display: flex;
    justify-content: space-around;
    flex-grow: 1;
    width: 100%;
    align-self: center;
  }

  #resumeEditor {
    width: 35%;
    background: #444;
    border-radius: 5px;
  }

  #resumePreview {
    background: #777;
    border-radius: 5px;
    margin-left: 16px;
    flex-grow: 1;
  }
</style>
