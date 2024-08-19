<script>
    import Header from '../lib/Header.svelte';
    import Links from '../lib/Links.svelte';
    import Degrees from '../lib/SelectedDegrees.svelte';
    import Table from '../lib/Table.svelte';

    let selectedPage = "1";
</script>


<main>
    <div class="head">
        <Header/>
    </div>
    <div class="body">
        <div class="left-panel">
            <Table />
        </div>
        <div class="right-panel">
            <div class="boxes">
                <Degrees/>
                <Links/>
            </div>
        </div>
    </div>
</main>

<style>
    main {
        border-style: dashed;
        font-family: "Comic Sans MS", cursive, sans-serif;
        background-color: black;
        color: #84c754;
    }

    .head {
        border-style: solid;
    }

    .body {
        border-style: solid;
        display: flex;
        justify-content: center;
        padding: 1%
    }

    .left-panel {
        width: 85%;
    }
    .right-panel {
        width: 15%;
    }

    .boxes {
        width: 100%;
    }
</style>