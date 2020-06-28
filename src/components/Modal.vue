<template>
  <div>

      <div class="md-modal" v-bind:class="{'md-show':mdShow}">
          <div class="md-modal-inner">
            <div>
              <button class="md-close" @click="closeModal">close</button>
            </div>
            <div class="md-content">
              <div class="confirm-tips">
                <slot name="message"></slot>
              </div>
              <div class="btn-wrap">
                <slot name="btnGroup"></slot>
              </div>
            </div>
          </div>
      </div>

      <div class="md-overlay" v-if="mdShow" @click="closeModal">
        
      </div>
    <div>
      hahhah
    </div>
  </div>
</template>

<script>
export default {
    name:"Modal",
    props:["mdShow"],
    data(){
        return{
            
        }
    },
    methods:{
        closeModal(){
            this.$emit("close")
        }
    }
}
</script>

<style scoped>
.md-modal {
  position: fixed;
  top: 50%;
  left: 50%;
  width: 535px;
  height: auto;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  visibility: hidden;
  z-index: 201;
}

.md-modal .md-close {
  position: absolute;
  top: 7px;
  right: 7px;
  width: 34px;
  height: 34px;
  -webkit-transform: scale(0.5);
  -ms-transform: scale(0.5);
  transform: scale(0.5);
  text-indent: -8000px;
}
.md-modal .md-close:before, .md-modal .md-close:after {
  position: absolute;
  top: 16px;
  left: -4px;
  content: "";
  width: 44px;
  height: 3px;
  background: #d7d8dd;
  -webkit-transition: -webkit-transform .5s ease-out;
  transition: -webkit-transform .5s ease-out;
  transition: transform .5s ease-out;
  transition: transform .5s ease-out, -webkit-transform .5s ease-out;
}
.md-modal .md-close:before {
  -webkit-transform: rotate(-45deg);
  -ms-transform: rotate(-45deg);
  transform: rotate(-45deg);
}

.md-modal .md-close:after {
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

.md-modal .md-close:hover:before, .md-modal .md-close:hover:after {
  -webkit-transition: -webkit-transform .3s ease-out;
  transition: -webkit-transform .3s ease-out;
  transition: transform .3s ease-out;
  transition: transform .3s ease-out, -webkit-transform .3s ease-out;
}

.md-modal .md-close:hover:before {
  -webkit-transform: rotate(-135deg);
  -ms-transform: rotate(-135deg);
  transform: rotate(-135deg);
}

.md-modal .md-close:hover:after {
  -webkit-transform: rotate(-45deg);
  -ms-transform: rotate(-45deg);
  transform: rotate(-45deg);
}
.md-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 200;
}

.md-modal .md-modal-inner {
  padding: 40px 30px;
  background: #fff;
  -webkit-transform: translateY(20%);
  -ms-transform: translateY(20%);
  transform: translateY(20%);
  opacity: 0;
  -webkit-transition: all .3s ease-out;
  transition: all .3s ease-out;
}

.md-modal.md-show {
  visibility: visible;
}

.md-modal.md-show .md-modal-inner {
  -webkit-transform: translateY(0);
  -ms-transform: translateY(0);
  transform: translateY(0);
  opacity: 1;
  -webkit-transition: all .5s ease-out;
  transition: all .5s ease-out;
}
.md-content{
  margin: 0 auto;
  width: 200px;
  height: 100px;
  border: 1px solid;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

  


</style>