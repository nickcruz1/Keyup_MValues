<!-- Have Key up work for multiple values grabbed from multiple input values... put them into template literals? -->
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

  <!-- Keyup Test Currently Conducting -->
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
      let mGroupText = document.querySelectorAll(".mGroup");
       let mGroupPass = document.querySelectorAll(".mGroup");
        let mGroupNum = document.querySelector(".mGroup");
      let mGroupOutput = document.getElementById("mGroupOutput");
      
      let mGroupOutput1 = document.querySelectorAll(".mGroup").value;
      
    mGroupOutput.innerHTML = (mGroupOutput1);
      
    },
    alertMe() {
      alert("Hello");
    }
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
