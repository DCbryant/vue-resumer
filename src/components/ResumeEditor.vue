<template>
  <div id="resumeEditor">
      <nav>
          <ol>
              <li v-for="(item,index) in resume.visibleItems"
                :class="{active: item === selected}"
                @click="selected = item"
                :key="index"
              >
                {{index}}
              </li>
          </ol>
          <ol class="panels">
                <li v-for="(item,index) in resume.visibleItems" v-show="item === selected" :key="index">
                    {{resume[item]}}
                </li>
          </ol>
      </nav>
  </div>
</template>

<script>
export default {
  data:function(){
      return{
          selected:'bio',
          resume:{
              visibleItems: ['bio', 'work history', 'education', 'projects', 'awards', 'contacts', 'others'],
              bio:{
                  name:'',
                  city:'',
                  title:''
              },
              'work history': [],
              education: [],
              projects: [],
              awards: [],
              contacts: [],
              others: []
          }
      }
  }
}
</script>

<style lang="scss">
    #resumeEditor{
        background-color: #fff;
        box-shadow:0 1px 3px 0 rgba(0,0,0,0.25);
        display: flex;
        flex-direction: row;
        overflow: auto;
        >nav{
            width: 80px;
            background-color: #000;
            color: #fff;
        }
        >ol{
            >li{
                height: 48px;
                display: flex;
                justify-content: center;
                align-items: center;
                margin-top: 16px;
                margin-bottom: 16px;
                &.active{
                    background-color: #fff;
                    color: #000;
                }
            }
        }
    }
    ol{
        list-style: none;
    }
</style>



