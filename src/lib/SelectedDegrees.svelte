<script>
    let selectedDegrees = [
        "Computer Science, BA",
        "Data Science, BS",
        "Mathematics Minor",
        "Economics Minor"
    ];

    function addDegree() {
        let newDegree = prompt("Enter Degree Title");
        if (newDegree != null && newDegree.trim() !== "") {
            selectedDegrees = [...selectedDegrees, newDegree];
        }
        else {
            window.alert("Not a valid input.");
        }
    }
    function removeDegree() {
        let removeID = Number(prompt("Enter Degree # to remove"));
        if (isNaN(removeID) || removeID > selectedDegrees.length || removeID <= 0){
            window.alert("Not a valid ID.");
        }
        else {
            selectedDegrees.splice(removeID-1, 1);
            selectedDegrees = [...selectedDegrees];
        }
    }
</script>

<main>
    <nav>
        <h3>Selected Degrees</h3>
        <ol>
        {#each selectedDegrees as item}
            <li>{item}</li>
        {/each}
        </ol>
    </nav>
    <div class="buttons">
        <button on:click={addDegree}>
            Add Degree
        </button>
        <button on:click={removeDegree}>
            Remove Degree
        </button>
    </div>
</main>

<style>
    main{
        padding: 5%;
        margin: 5%;
        border-style: solid;
        height: 350px;
    }
    ol {
        color: white;
        margin: 0%;
        padding: 0% 0% 15%;
        list-style-type: none;
    }
    h3 {
        margin: 0% 0% 7%;
    }
    .buttons{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>