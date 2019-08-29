# Transition-Vue
HTML
<div id="app">
  <div class="container">
    <div class="row">
    <div class="col">
      <h1>Perk List</h1>
      <hr>
      <button class="btn btn-primary" @click="show = !show">
        Show Choices 
      </button>
      <br><br>
      <transition name="fade">
        <div class="alert alert-info" v-show="show">
          Charisma
        </div>
      </transition>
      <transition name="slide" type="animation">
        <div class="alert alert-info" v-if="show">
          Technology 
        </div>
      </transition>
      <transition name="fade" appear>
        <div class="alert alert-info" v-if="show">
          Weaponary 
        </div>
      </transition>
    </div>
  </div>
</div>
JavaScript/Vue
 var app = new Vue({
  el: '#app',
  data: function() {
    return {
      show: true
    }
  }
})
  CSS
  .fade-enter {
  opacity: 0;
}
.fade-enter-active {
  /* opacity: 1; default already is 1 */
  transition: opacity 1s;
}
.fade-leave {
  /* opacity: 1; default already is 1 */
}
.fade-leave-active {
  opacity: 0;
  transition: opacity 1s;
}

.slide-enter {
  opacity: 0;
  /* transform: translate(20px); */
}
.slide-enter-active {
  animation: slide-in 1s ease-out forwards;
  transition: opacity .5s;
}
.slide-leave {
  
}
.slide-leave-active {
  animation: slide-out 1s ease-out forwards;
  opacity: 0;
  transition: opacity 3s;
}

@keyframes slide-in {
  from {
    transform: translateY(20px);
  }
  to {
    transform: translateY(0);
  }
}

@keyframes slide-out {
  from {
    transform: translateY(0)
  }
  to {
    transform: translateY(20px)
  }
}
