<template>
  <div class="">
    <h1>Helo world</h1>
    <p>{{ greeting }} {{ name }}</p>
    <h5 v-text="blog">Hello owl</h5>
    <div class="" v-html="fullname"></div>
    <div class="" v-html="alert"></div>
    <h2 v-bind:id="heading">ini heading</h2>
    <button v-bind:disabled="isDisable">Tombol</button>
    <h2 class="underline" :class="danger">this is underlined</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movue</h2>
    <h2 v-bind:class="isSouldOut ? 'sould-out' : 'new'">souldout? Movie</h2>
    <h2 v-bind:class="['new', 'promoted']">newly Promoted Movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSouldOut ? 'sould-out' : 'new']">Array kondition</h2>

    <h2
      v-bind:class="{
        promoted: isPromoted,
        new: !isPromoted,
        'sould-out': isSouldOut,
      }"
    >
      Object Condition
    </h2>

    <h2
      :style="{
        color: highlightColor,
        'font-size': headerSize + 'px',
        padding: '30px',
        'background-color': 'aqua',
      }"
    >
      Inline style
    </h2>

    
    <h2 :style="headerStyleObject">style Object</h2>
    <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
    <div :style="[baseStyleObject, DangerStyleObject]">Danger Style</div>
    
    
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      // binding text
      name: "vrindavan",
      greeting: "Hello ",
      blog: "lorem ipsum sauh nasssa ",
      // binding HTML
      fullname: "<b>KavinSebastian</b>",
      alert: `<a href="#" onclick="alert('you have been hacked!')" > Win a Prize !</a>`,
      // binding attributes
      headingId: "heading",
      isDisable: true,
      // binding classes
      status: "danger",
      isPromoted: true,
      isSouldOut: true,
      // binding style
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: "orange",
        fontSize: "50px",
        padding: "20px",
        "background-color": "grey",
      },
      baseStyleObject:{
        fontSize:'50px',
        padding:'10px'
      },
      successStyleObject:{
        color:'green',
        backgroundColor:'lightgreen',
        border:'1px solid green',
        padding:'20px'
      },
      DangerStyleObject:{
        color:'darked',
        backgroundColor:'red',
        border:'1px solid darked',
        padding:'20px'
      }
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sould-out {
  color: red;
}
</style>
