<script>
    import { onMount } from 'svelte'
    // import TransitionWrapper from '../components/TransitionWrapper.svelte'

    onMount(() => {
        const formElement = document.querySelector('#contact-form')
        formElement.addEventListener('submit', (event) => {
            event.preventDefault()
            const data = new URLSearchParams(new FormData(formElement))
            fetch('https://getform.io/f/79785995-42a5-4117-a701-1905eeab20f9', {
                method: 'POST',
                body: data
            })
            alert('thank you for submitting!')
        })
    })
</script>



<form id="contact-form" action="https://getform.io/f/79785995-42a5-4117-a701-1905eeab20f9" method="POST">
    <label for="fullname">Your full name</label>
    <input type="text" id="fullname" name="fullname"><br>
    <label for="email">Your email</label>
    <input type="email" id="email" name="email"><br>
    <label for="message">Your message</label>
    <input type="text" id="message" name="message"><br>
    <button>Submit</button>
</form>
