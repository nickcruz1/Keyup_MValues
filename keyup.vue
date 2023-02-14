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
