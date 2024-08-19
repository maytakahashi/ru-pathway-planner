<script>
    import catalog from '../courses.json';
    
    /**
	 * @param {string | null} id
	 */
    function findCourseById(id) {
        return catalog.find(course => course.id === id) || null; // Return null if no course with that ID is found
    }

    // const course1 = {
    //     id: "01:198:111",
    //     name: "Intro to CS",
    //     prereqs: [],
    //     credits: 4,
    //     gened: "qq"
    // }
    
    // const course2 = {
    //     id: "01:198:112",
    //     name: "Data Structures",
    //     prereqs: [course1],
    //     credits: 4,
    //     gened: "qq"
    // }
    
    // const course3 = {
    //     id: "01:198:205",
    //     name: "Discrete Structures",
    //     prereqs: [course1, course2],
    //     credits: 4,
    //     gened: "qq"
    // }

    $: courses = [findCourseById("01:640:478.44"), findCourseById("01:640:026.2"), findCourseById("01:640:130.11")].filter(course => course !== null);

    const addCourse = () => {
        let newCourse = findCourseById(prompt("Enter Course ID"));
        if (newCourse != null) {
            if (courses.includes(newCourse)){
                window.alert("Course is already in table.");
            }
            else {
                courses = [...courses, {id: newCourse.id, name: newCourse.name, credits: newCourse.credits}];
            }
        }
        else {
            window.alert("Not a valid course ID.");
        }
    }
    const removeCourse = () => {
        let removeID = Number(prompt("Enter Degree # to remove"));
        if (isNaN(removeID) || removeID > courses.length || removeID <= 0){
            window.alert("Not a valid ID.");
        }
        else {
            courses.splice(removeID-1, 1);
            courses = [...courses];
        }
    }

</script>

<main>
    <table>
        <tr>
            <th>ID</th>
            <th>Course Title</th>
            <th>Prereqs</th>
            <th>Credits</th>
            <th>GenED Req's</th>
        </tr>
        {#each courses as item}
        <tr>
            <td>{item.id}</td>
            <td>{item.name}</td>
            <td>
                <!-- {#if item.prereqs.length>0}
                    {item.prereqs.map((/** @type {{ name: any; }} */ prereq) => prereq.name).join(', ')}
                {:else}
                    None
                {/if} -->
                Unknown
            </td>
            <td>{item.credits}</td>
            <td>
                <!-- {item.gened} -->
                 Unknown
            </td>
        </tr>
        {/each}
    </table>
    <div class="buttons">
        <button on:click={addCourse}>Add course</button>
        <button on:click={removeCourse}>Remove course</button>
    </div>
</main>

<style>
    table {
        margin: 2%;
        width: 95%;
        padding: 2%;
        background-color: #c3d7de;
    }

    tr {
        display: flex;
        flex-direction: row;
        width: 100%;
    }

    th{
        margin: 0% 0% 1%;
        color: #2B2D42;
    }
    td{
        margin: .5% 0%;
        color: #54647f;
    }
    td, th{
        flex: 1;
        text-align: left;
    }

        
    td:nth-child(1), th:nth-child(1) {
    flex: .8;
    }

    td:nth-child(2), th:nth-child(2) {
    flex: 2;
    }

    td:nth-child(3), th:nth-child(3)  {
    flex: 1.5;
    }

    td:nth-child(4), th:nth-child(4), td:nth-child(5), th:nth-child(5){
    flex: 1;
    }

    .buttons {
        display: flex;
        justify-content: center;
    }

    button{
        margin: 0% 1%;
    }
</style>