<script lang="ts">
	let symptoms = ['Headache','another one','and another'];
    let currentSymptom =''
    let error=false
    let addSymptom = () =>{
        if(!currentSymptom){
            error=true
        }
        symptoms=[...symptoms,currentSymptom]
        currentSymptom=''
    }
</script>

<div class="mainContainer">
	<div class="header-container">
		<h1>Add Symptoms</h1>
		<button>save</button>
	</div>
	<main>
        {#each symptoms as todo,index}
            <div class="todo">
                {index+1}.{todo}
            </div>
        {/each}
    </main>
	<div class={"enterToDo" + (error ? "errorBorder" :" ")}>
		<input bind:value={currentSymptom} type="text" placeholder="Enter Symptoms" id="" />
		<button on:click={addSymptom}>ADD</button>
	</div>
</div>

<style>
	.mainContainer {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		gap: 24px;
		padding: 24px;
		width: 100%;
		max-width: 1000px;
		margin: 0 auto;
	}
	.header-container {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.header-container button {
		background-color: #003c5b;
		color: white;
		padding: 10px 12px;
		border: none;
		border-radius: 5px;
		cursor: pointer;
	}
	main {
		display: flex;
		flex-direction: column;
		gap: 8px;
		flex: 1;
	}
	.enterToDo {
		display: flex;
		align-items: stretch;
		border: 1px solid white;
	}
	.enterToDo input {
		background: transparent;
		border: none;
		padding: 14px;
		color: white;
		flex: 1;
	}
	.enterToDo input:focus {
		outline: none;
	}
	.enterToDo button {
		padding: 0 14px;
		background-color: #003c5b;
		border: none;
		color: white;
		font-weight: 600;
		cursor: pointer;
	}
	.enterToDo button:hover {
		background: transparent;
	}
</style>
