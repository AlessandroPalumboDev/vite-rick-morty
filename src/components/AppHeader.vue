<script>
export default {
    name: 'AppHeader',
}
</script>
<template>
    <h1>Rick and Morty App</h1>
    <div class="nav">
        <input type="text" placeholder="Search character">
        <select name="Search" id="select" >
          <option value="0">Select status</option>
        </select>
        <button id="search">Search</button>
        <button id="reset">Reset</button>
    </div>
</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables';
h1 {
  text-align: center;
  font-weight: 900;
  margin: 20px 0 40px 0;
}
.nav{
    text-align: center;

    button, select, input{
        padding: 10px;
        border: 1px solid lightgray;
        border-radius: 10px;
        margin-inline: 10px;

    }
    #reset{
        background-color: orange;
            &:hover{
                background-color: rgb(179, 117, 1);
                box-shadow:variables.$ombra-bottone;
                color: white;
                cursor: pointer;
                
            }
    }
    #search{
        background-color: rgb(1, 106, 243);
        color: white;

        &:hover{
            background-color: rgb(2, 73, 165);
            box-shadow:variables.$ombra-bottone;
            cursor: pointer;
        }
    }

}
</style>