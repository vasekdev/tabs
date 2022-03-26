<template>
<span class="redText"> ------------------ HelloWorldComponent-start (vue) ------------------ </span>
  <div class="hello">
    <h3>{{ msg }}</h3>
    <p>
      <a href="javascript:void(0)" @click="addWindow('https://www.bbc.com/news','BBC')">BBC</a> | 
      <a href="javascript:void(0)" @click="addWindow('https://www.reuters.com','Reuters')">Reuters</a> | 
      <a href="javascript:void(0)" @click="addWindow('https://www.yahoo.com','DW')">DW</a><br />
      <a href="javascript:void(0)" @click="closeWindows">sign out</a>
    </p>
  </div>
  <span class="redText"> ------------------ HelloWorldComponent-end  (vue) ------------------ </span>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    addWindow: function(url, windowValue){
        console.log(" url: " + url + 'addWindow: ' + windowValue);
        var windowsArray = [];

        window.open(url, windowValue);
        console.log("addItemToWindowsStorage");

        if (localStorage.getItem("storedWindows") === null) {
          console.log("is null");
          // e.g. googleWindow
          localStorage.setItem("storedWindows", windowValue);
          // add winGoogle to array
          windowsArray.push(windowValue);
          // stringify array value
          localStorage.setItem("storedWindows", JSON.stringify(windowsArray));
          // retrieve
          console.log(JSON.parse(localStorage.getItem("storedWindows")));
        } else {
          console.log("is NOT null");
          // get window list
          windowsArray = JSON.parse(localStorage.getItem("storedWindows"));
          // add winGoogle to array
          windowsArray.push(windowValue);
          // stringify array value
          localStorage.setItem("storedWindows", JSON.stringify(windowsArray));
          // retrieve
          console.log(JSON.parse(localStorage.getItem("storedWindows")));
        }
    },
    closeWindows: function(){
      // disable pop-up blocker
      console.log(' (HWC) closeWindows... ');
      var storedWindowsArray = JSON.parse(localStorage.getItem("storedWindows"));
      var newWindowObj = null;

      // retrieve
      console.log("(HWC) STORED-WINDOWS: " + storedWindowsArray);

      for (var i = 0; i < storedWindowsArray.length; i++) {
        console.log("closing  [" + [i] + "] " + storedWindowsArray[i]);
        var newWindowObj = window.open("", storedWindowsArray[i]);
        if (newWindowObj != null) {
          newWindowObj.close();
        }
      }

      console.log("removing storedWindows from localstorage");
      localStorage.setItem("storedWindows", "");
      console.log(
        "printing storedWindows: " + localStorage.setItem("storedWindows", "")
      );
      localStorage.removeItem("storedWindows");

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.redText{
  color: red;
}
</style>
