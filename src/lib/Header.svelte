<script>
    let selectedPage = "1";
    const setPage = (/** @type {string} */ pageNum) => selectedPage = pageNum;
</script>

<main>
    <nav>
        <div id="logo">
            <img src="full-logo.png" alt="LOGO" />
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
        padding: 0% 1%;
    }

    #logo img {
        height: 80px;
        border-color: #2b2d42; 
        padding: 10px;
        margin: 1% 0% 0%;
    }

    .links {
        /* border-style: solid #8d99ae; */
        display: flex;
        justify-content: center;
        gap: 10%;
        padding: 1%;
        list-style-type: none;
        background-color: #e84255;
    }

    .links button {
        text-decoration: none;
        border: none;
        background: none;
        font-size: 1em;
        cursor: pointer;
        color: #edf2f4;
    }

    .bold {
        font-weight: bold;
    }

    button:hover {
        text-decoration: underline;
        color: #f3bed0; 
    }
</style>
