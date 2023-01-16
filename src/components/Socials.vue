<template>
    <div class="card">
       <button>
        <a href="">GitHub</a>
       </button>

       <button>
        <a href="">Twitter</a>
       </button>
    </div>
</template>

<style scoped>
button {
  border: 1px solid cornflowerblue;
  background-color: transparent;
  color: #ccd7ea;
  margin-inline: .5rem;
  border-radius: 4px;
  padding: .5rem 1rem;
  transition: all ease-in-out 0.3s;
  box-shadow: -5px 5px cornflowerblue;
}

button:hover {
  box-shadow: -3px 3px cornflowerblue;
  cursor: pointer;
}
.card {
    /* border-left: 1px solid greenyellow;
    background-color: #99ff000e; */
    padding: 1rem;
}

.card p { margin-block: .5rem; }

.card a { 
    color: #ccd7ea;
    text-decoration: none;
}
</style>