<script>
    import Header from '../lib/Header.svelte';
    import Links from '../lib/Links.svelte';
    import Degrees from '../lib/SelectedDegrees.svelte';
    import Table from '../lib/Table.svelte';

    let selectedPage = "1";
</script>

<main>
    <header>
        <Header/>
    </header>
    <div class="bottom">
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
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        background-color: #2b2d42;
        color: #edf2f4; 
    }

    header {
        border-style: solid;
        border-color: #8d99ae;
    }

    .bottom {
        border-style: solid;
        border-color: #8d99ae; 
        display: flex;
        justify-content: center;
        padding: 1%;
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
