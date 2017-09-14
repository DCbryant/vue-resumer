<template>
  <div class="page">
    <header>
      <Topbar/>
    </header>
    <main>
      <ResumeEditor/>
      <ResumePreview/>
    </main>
  </div>
</template>

<script>
import 'normalize.css'
import './assets/reset.css'

import Topbar from './components/Topbar'
import ResumeEditor from './components/ResumeEditor'
import ResumePreview from './components/ResumePreview'

export default {
  name: 'app',
  data: function(){
    return {
      text: '你好'
    }
  },
  components: {Topbar, ResumeEditor, ResumePreview}
}
</script>

<style lang="scss">
  .page{
    height: 100vh;
    display: flex;
    flex-direction: column;
    background-color: #EAEBEC;

    >main{
      flex-grow: 1;
    }
    >main{
        min-width: 1024px;
        max-width: 1440px;
        margin: 16px 0;
        padding: 0 16px;
        align-self: center;
        width: 100%;
        display: flex;
        justify-content: space-between;
    }
  }
  
  #resumeEditor{
    width: 35%;
    background-color: #444;
  }
  #resumePreview{
     flex-grow: 1;
     margin-left: 16px;
     background-color: #777;
  }

</style>

