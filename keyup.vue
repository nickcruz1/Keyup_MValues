<!-- Have multiple values not submit unless all 3 values have been entered -->
<!-- Use an 'if-else' statement for this -->

<template>
  <div id="app">
    <div class="container">
     
      <label for="input">Please enter input below:</label>
      <br />
      <input @keyup.enter="keySubmit" class="theInput" type="text" />
      <br />

      <div class="lContainer">
        <label for="infoSubmitted">The Value Submitted is:</label>
        <div class="output"></div>
        <a @click="reset" class="reset" href="#">Reset &#8634;</a>
      </div>
      <h3 class="otherOutput"></h3>
    </div>
    
  
    <div class="mContainer">
      
      <label for="text">Enter Text Here:</label>
      <input class="mGroupText" @keyup.enter="addGroup" type="text">
       <label for="password">Enter Password Here:</label>
      <input class="mGroupPass" @keyup.enter="addGroup" type="password">
      <label for="number">Enter Number Here:</label>
      <input class="mGroupNum" @keyup.enter="addGroup" type="number">
      
      <div id="mGroupOutput"></div>
      
    </div>
   
    
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "Welcome to Vue!",
    };
  },
  methods: {
    reset() {
      let output = document.querySelector(".output");
      let otherOutput = document.querySelector(".otherOutput");

      otherOutput.innerHTML = "The values have been reset!";
      setTimeout((myReset) => {
        output.innerHTML = "";
        otherOutput.innerHTML = "";
      }, 2000);
    },
    myReset() {
      let output = document.querySelector(".output");
      let otherOutput = document.querySelector(".otherOutput");
      output.innerHTML = "";
      otherOutput.innerHTML = "";
    },
    keySubmit() {
      let input = document.querySelector(".theInput");
      let output = document.querySelector(".output");

      output.innerHTML = input.value.toUpperCase();
      input.value = "";
    },
    addGroup() {
      let mGroupText = document.querySelector(".mGroupText");
       let mGroupPass = document.querySelector(".mGroupPass");
        let mGroupNum = document.querySelector(".mGroupNum");
      let mGroupOutput = document.getElementById("mGroupOutput");
      
    let mGroup = [
      mGroupText.value, mGroupPass.value, mGroupNum.value 
    ]
      
    mGroupOutput.innerHTML = `
    <div class="mvContainer">
    <h2 class="mvText"> Multiple Value Submissions</h2>
    <h5 class="blueText">The Text Value is:${mGroup[0]}</h5> \<br>\
    <h5 class="redText">The Password Value is:${mGroup[1]}</h5> \<br>\
    <h5 class="greenText">The Number Value is:${mGroup[2]}</h5>  
    </div>`; 
      
    },
  mounted() {
    console.log("Logged On mount")
  }
};
</script>

<style>
body {
  background-color: lightgray;
}

.container {
  display: flex;
  flex-direction: column;
  margin: auto;
  width: 400px;
  border: 1px solid black;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  position: absolute;
  padding: 2rem;
  border-radius: 15px;
}

label,
.output {
  margin-left: 5px;
}

.output {
  color: red;
  font-weight: bolder;
}

input {
  margin: auto;
  width: 50%;
}

.lContainer {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.reset {
  text-decoration: none;
  margin-left: 20px;
}

.reset:hover {
  color: red;
  cursor: pointer;
}

.otherOutput {
  text-align: center;
  margin-top: 1rem;
  color: blue;
}
  
  .mContainer {
    display: flex;
    width: 300px;
    flex-direction: column;
    margin: 1rem auto 1rem auto;
  }
  
  .mContainer button {
    margin: 10px auto 10px auto;
    border-radius: 10px;
    padding: 5px;
    width: 200px;
  }
  
  .mContainer button:hover {
    cursor: pointer;
    background-color: blue;
    color: white;
    border: 2px solid white;
  }
  
  .mvContainer {
    display: flex;
    margin: 1rem;
    padding: 1rem;
    justify-content: center;
    flex-direction: column;
    border: 1px solid black;
  }
  
  .mvText {
    text-align: center;
    font-size: 1rem;
    text-decoration: underline;
  }
  
  .blueText {
    color: blue;
  }
  
  .redText {
    color: red;
  }
  
  .greenText {
    color: lightgreen;
  }
  
</style>
