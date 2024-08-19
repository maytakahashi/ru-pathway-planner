<script>
    import Header from '/Users/maytakahashi/Desktop/schedule-project/src/lib/Header.svelte';
    import Links from '/Users/maytakahashi/Desktop/schedule-project/src/lib/Links.svelte';
    import Degrees from '/Users/maytakahashi/Desktop/schedule-project/src/lib/SelectedDegrees.svelte';
    import Table from '/Users/maytakahashi/Desktop/schedule-project/src/lib/Table.svelte';

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