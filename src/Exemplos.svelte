 
<!-- svelte-ignore css-unused-selector -->
<script>
	let src = 'image.gif';
    let name = 'Rick Astley';
    let rand;
    let string = `Aproveite o <strong>GIF!!!</strong>`;
    let color='primary';
    let invi= '⠀⠀⠀⠀';
    let invi2= '⠀⠀⠀⠀';

        $: dobro = rand *2;
        $: quadruplo = dobro*2;
    function setRandom(){
        rand = Math.random();
         {rand <0.5 ? color='success' : color ='danger'}     
    }
    function showDobro(){
        invi = dobro
    }
    function showQuadruplo(){
        invi2 = quadruplo
    }
    $: if (quadruplo > 2)
        alert('ta ficando alto o número')

</script>

<div class="container-fluid" style="background-color:yellow">
 
    <div class="row-1">
        <div class="col-2-1">
            <img {src} alt="{name} dancing" width="240" height="280">    
            <p>{@html string}</p>
        </div>
        <div class="col-2-2">
            <div class="row">
                <div class="col-6">
                    <botton type="botton" style="margin:3px" class="btn btn-primary"on:click={setRandom}>Clique parar gerar um número</botton>
                </div>
                <div class="col-6">
                    <botton type="botton"style="margin:3px" class="btn btn-{color}">{rand}</botton>
                </div>
            </div>
            <div class="row">
                <div class="col-6">
                    <botton type="botton" style="margin:3px" class="btn btn-dark"on:click={showDobro}>Dobro do número</botton>
                </div>
                <div class="col-6">
                    <botton type="botton"style="margin:3px" class="btn btn-dark">{invi}</botton>
                </div>
            </div>
            <div class="row">
                <div class="col-6">
                    <botton type="botton" style="margin:3px" class="btn btn-primary"on:click={showQuadruplo}>Quadruplo do número</botton>
                </div>
                <div class="col-6">
                    <botton type="botton"style="margin:3px" class="btn btn-light">{invi2}</botton>
                </div>
            </div>
            
        
        </div>

    </div>
 
</div>

<style>
    .row-1{
        display: grid;
       grid-template-rows: 1fr;
       grid-template-columns: 1fr 1fr;
       grid-template-areas: "a b";
       height: 70vh;
       background: green;
       justify-items: center;

    }
    .col-2-1{
        grid-area: a;
        background-color: aqua;
        font-weight: 100;
        width: 100%;
        text-align: center;
 
    }
    .col-2-2{
        grid-area: b;
        background-color: blue;
        font-weight: 100;
        text-align: center;
        width: 80%;
    }
</style>