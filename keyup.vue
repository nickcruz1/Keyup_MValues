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
