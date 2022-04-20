<svelte:head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono" rel="stylesheet"> 
</svelte:head>

<script>
    import FaGithub from 'svelte-icons/fa/FaGithub.svelte'
    import IoLogoLinkedin from 'svelte-icons/io/IoLogoLinkedin.svelte'
    import MdEmail from 'svelte-icons/md/MdEmail.svelte'
    import Typewriter from 'svelte-typewriter'
    import MdWork from 'svelte-icons/md/MdWork.svelte'
    const typewriterText = [
        "DevOps / SRE engineer",
        "Bope"
    ]
    let selected;
    const categories = [
        "Work experience",
        "Volunteering",
        "Education",
        "Skills"
    ]
</script>

<div class="layout">
    <div class="greetings">
        <p>Hello there!</p>
        <h4>I am Bastien Jeannelle</h4>
        <Typewriter loop={3000} cursor="white">
            {#each typewriterText as text} 
                <p>{text}</p>
            {/each}
        </Typewriter>
    </div>
    <div class="about">
        <p><img src="icons/work.svg" alt="work" width=30>   DevOps Engineer at <a href="https://sharpershape.com/">SharperShape</a></p>
        <p><img src="icons/student.svg" alt="studies" width=30>   Studied in 4 countries, worked in 2.</p>
        <p><img src="icons/code.svg" alt="code" width=30>   Code in Go, Javascript, Python and a lot of ESPs / arduinos.</p>
        <p><img src="icons/love.svg" alt="love" width=30>   Healthcare, Environment, Fintech.</p>
    </div>
    <div class="skills">
        <select bind:value={selected}>
            {#each categories as category}
            <option value={category}>
				{category}
			</option>
		{/each}
	</select>

    </div>
</div>

<footer>
    <div class="networks">
        <a href="https://github.com/Sonlis"><div class="icon"><FaGithub /></div><span>Github</span></a>
        <a href="https://github.com/Sonlis"><div class="icon"><IoLogoLinkedin /></div><span>Linkedin</span></a>
        <a href="mailto:bastien.jeannelle@gmail.com"><div class="icon"><MdEmail /></div><span>Email</span></a>
    </div>
</footer>



<style>
    .layout {
	display: grid;
    grid-template-columns: 50% 50%;
    grid-template-rows: 50% 50%;
    height: 85vh;
    width: 100%;
    background-color: rgba(31, 41, 55);
    }
    .about {
        grid-column: 1;
        grid-row: 2;
        
    }
    .about p {
        font-size: 1em;
        margin-top: 3%;
        margin-left: 10%;
    }
    .about a {
        color: inherit;
    }
    .greetings {
        grid-column: 1;
        grid-row: 1;
        margin-top: 9%;
        margin-left: 9%;
    }
    .skills {
        grid-row: 1;
        grid-column: 2;
    }
   
    p, h2, h4 {
        font-family: Roboto mono;
        font-weight: bold;
        color: white;
    }
    h4 {
        font-size: 28px;
        letter-spacing: 2px;
    }
    p {
        font-size: 18px;
    }
    span {
        margin-top: 3%;
        margin-left: 10%;
    }
    .networks a {
        text-decoration: none;
        color: inherit;
        background-color: rgba(31, 41, 55, 1);
        border-style: strong;
        border-radius: 12px;
        padding-right: 4%;
        padding-left: 4%;
        padding-top: 2%;
        padding-bottom: 1.2%;
        display: inline-flex;
        color: white;
        font-size: 18px;
        font-weight: bold;
        margin-left: 5%;
        transition-property:background-color;
        transition-duration:0.8s;
    }
    footer {
        background-color: rgba(107, 114, 128, 1);
        margin: 0;
    }
    a:hover {
        background-color: rgba(31, 41, 55, 0.3);
    }
    .icon {
        color: white;
        width: 32px;
        height: 32px;
    }
    .networks {
        margin-top: 2%;
        margin-left: 20%;
    }
    .skills {

    }
</style>