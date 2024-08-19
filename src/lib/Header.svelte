<script>
    let selectedPage = "1";
    const setPage = (/** @type {string} */ pageNum) => selectedPage = pageNum;
</script>

<main>
    <nav>
        <div id="logo">
            <img src="Png.png" alt="LOGO" />
        </div>
        Page: {selectedPage}
        <ul class="links">
            <li><button class:bold={selectedPage == "1"} class:reg={selectedPage != "1"} on:click={() => setPage('1')}>COMPLETED COURSES</button></li>
            <li><button class:bold={selectedPage == "2"} class:reg={selectedPage != "2"} on:click={() => setPage('2')}>COMPILED SCHEDULE</button></li>
        </ul>
    </nav>
</main>

<style>
    nav {
        padding: 0% 1%
    }
    #logo img{
        height: 80px;
        width: 130px;
        border-style: solid;
        padding: 10px;
        margin: 1% 0% 0%;
        background-color: white;
    }
    .links {
        border: solid;
        display: flex;
        justify-content: center;
        gap: 10%;
        padding: 1%;
        list-style-type: none;
    }

    .links button {
        text-decoration: none;
        border: none;
        background: none;
        font-size: 1em;
        cursor: pointer;
    }
    .bold{
        font-weight: bold;
        color: #ffffff;
    }
    .reg{
        color: #ffffff;
    }
    button:hover {
        text-decoration: underline;
        color: #9cd772;
    }
</style>