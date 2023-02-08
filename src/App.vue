<template>
  <div class="fullcard">
  <h1>Steel Vengeance</h1>
  <img src="https://www.gannett-cdn.com/-mm-/c866a26832d9a00c13d83ca470f7860c9325bbed/c=0-18-2099-1204/local/-/media/2017/08/16/DetroitFreeP/DetroitFreePress/636384989754521386-SteelVengence-07.JPG">
  <p>Opening in 2018 at Cedar Point in Sandusky, Ohio, Steel Vengeance has quickly became a fan favorite.  Rocky Mountain Construction, a company that retracks old wooden roller coasters, came in to revamp Mean Streak and made it a hybrid roller coaster.  This means it has a wood structure, but the trains run along a steel track.  This allows for a better experience overall and increases the lifespan of older wooden roller coasters.  The ride is 205 feet tall with a 200 foot drop at 90 degrees and it flips you upside down four times.  The top speed of Steel Vengeance is 74 miles per hour and the total ride time is 2 minutes and 30 seconds.  Learn more about the ride by clicking below.</p>
    <button class="details">Details</button>
</div>
<button class="add" v-on:click="duplicator">Make a duplicate</button>

<button class="toggle" v-on:click="backColorChange">Background Color</button>

<button class="word" v-on:click="wordChanger">Words</button>

<button class="del" v-on:click="deleter">Remove Last</button>
</template>

<script>

let btn = document.querySelector('.add')
btn.addEventListener('mouseover', () => btn.style.backgroundColor= 'green'); 
btn.addEventListener('mouseover', () => btn.style.color= 'yellow'); 
btn.addEventListener('mouseout', () => btn.style.backgroundColor= 'red');
btn.addEventListener('mouseout', () => btn.style.color= 'white');
export default{
methods:{
 duplicator(){
  let d = document.querySelector('div');
  let cloneNode = d.cloneNode(true);
  document.body.appendChild(cloneNode);
  console.log(cloneNode);
},

 backColorChange(){
  var colors = document.querySelector(".fullcard");
  if (colors.style.backgroundColor === "black"){
    colors.style.backgroundColor = "blue";
  }else{
    colors.style.backgroundColor = "black";
  }
},

 wordChanger(){
  let thingy = document.querySelector('.word').forEach(thing);
  if(!thingy.innerHTML == "Something else"){
    thingy.innerHTML = "Something else";
  }
},


 deleter(){
  let d = document.querySelectorAll('div');
  var last = d[d.length- 1];
  if (d.length != 1){
  last.remove();
  }
},

 showhide(){
  var para = document.querySelector("p");
  if (para.style.display === "none"){
    para.style.display = "inline-block";
  }else{
    para.style.display = "none";
  }
}
}
}
</script>
<style>
.fullcard {
  border: 5px solid;
  text-align: center;
  color: white;
  margin: 12px;

  background-color: black;
  padding: 16px;
}
p{
  display: none;
}
img {
  max-width: 75%;
  max-height: 75%;
  margin: auto;
  display: block;
  padding: 16px, 16px;
}
button{
  padding: 8px 8px;
  color: blue;
  background-color: orange;
  text-transform: uppercase;
  display: none;
  margin: 8px;
}
.details{
  padding: 8px 8px;
  color: blue;
  background-color: orange;
  text-transform: uppercase;
  display: none;
  margin: 8px;
}
.add {
  padding: 8px 8px;
  color: white;
  background-color: red;
  text-transform: uppercase;
  margin: 8px;
}

.add:hover {
  background-color: green;
  color: yellow;
}

.add:focus{
  background-color: green;
  color: yellow;
}

.toggle{
  background-color: blue;
  color: orange;
}

@media screen and (min-width: 500px) and (max-width: 800px){
  button{
    display: inline-block;
  }
  .details{
    display: inline-block;
  }
}
@media (max-width: 500px) {
  div{
    font-size: 10px;
  }
}
</style>
