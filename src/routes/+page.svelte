<div class="page">
    <h1>Svelte 101</h1>

    <span class="val">
        {number}
    </span>

    <div class="buttons">
        <button on:click={addPlusOne} >+</button>
        <button on:click={subsctractMinusOne}>-</button>
    </div>

    <div class="custom-update buttons">
        <h3>Custom Update</h3>
        <input bind:value={updateValue} />
        <label>
        <input
                type="radio"
                name="operator"
                value="+"
                bind:group={selectedOperator}
        />
        +
        </label>
        <label>
            <input
                    type="radio"
                    name="operator"
                    value="-"
                    bind:group={selectedOperator}
            />
            -
        </label>
        <button on:click={()=>customOperation(selectedOperator,updateValue)}>Update</button>
    </div>

    <Component1 name="Kam"></Component1>

</div>



<style>
    page{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    h1 {
        text-align: center;
    }

    .val{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    }

    .buttons{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 1rem;
    }
</style>

<script lang="ts"   >
    import Component1 from './Component1.svelte'
    let number : Number = 0;
    let updateValue : Number = 0;
    let selectedOperator : String = '+';

    function addPlusOne(){
        number++;
    }

    function subsctractMinusOne(){
        number--;
    }

    function customOperation(operation:string, value:number){
        if(operation === '+'){
            number = Number(number) + Number(value);
        }else if(operation ==='-'){
            number = number - value;
        }
        updateValue = 0;
    }
</script>