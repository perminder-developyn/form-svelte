<script>
import axios from 'axios';

const sendForm = () => {
	if (contact.name && contact.email && contact.subject && contact.message) {
		axios.post(
		"https://api.developyn.com/public/contact-service/send",
		contact,
		{
			headers: {
				"x-api-key": "e6ccfc1f584a7341fdf5dd46ab9db95cf309bd78f9fcd93f1f9a73b9fa3fb007",
			},
		}
	);
	console.log('response');
	} else {
		console.log('error');
	}
}

const contact =  {
	id: '2BBBaXk9nlWATEaowPVP7gJdJGv',
	name: '',
	email: '',
	subject: '',
	message: ''
}
</script>

<main>
	<div class="content">
		<div class="heading">
			<h1 class="main-header">Learn to code by watching others</h1>
			<p class="sub-header">See how experienced developers solve problems in real-time. Watching scripted tutorials is great, 
			but understanding how developers think is invaluable. </p>
		</div>
		<div class="form-container">
			<button class="trial">
				<strong>Try it free 7 days</strong> then $20/mo. thereafter
			</button>
			<form name ="inputForm" id="form" class="form-input" action="javascript:void(0)" novalidate on:submit={sendForm}>
				<input type="text" bind:value={contact.name} placeholder="Name">
				<input type="email" bind:value={contact.email} placeholder="E-Mail">
				<input type="text" bind:value={contact.subject} placeholder="Subject">
				<input type="textarea" bind:value={contact.message} placeholder="Message" class="message">
				<button class="claim" type="submit">Send Your Message</button>
				<div class="t-c">
					<p class="terms"> By clicking the button, you are agreeing to our  &nbsp; 
						<span class="conditions"> Terms and Services</span> 
					</p>
				</div>
			</form>
		</div>
	</div>
	<footer>
		<p class="attribution">
			Challenge by 
			<a href="https://www.frontendmentor.io?ref=challenge" target="_blank">
				Frontend Mentor
			</a>. 
			Coded by 
			<a href="#">
				Perminder
			</a>.
		</p>
	</footer>
</main>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap");

main {
	background: hsl(0, 100%, 74%)  url(/images/bg-intro-desktop.png);
	font-family: 'Poppins';
	font-size: 16px;
}

.attribution { 
	bottom: 0;
	font-size: 11px; 
	text-align: center; 
}

.attribution a { 
	color: hsl(228, 45%, 44%); 
}

button {
	width: 100%;
	color: white;
	border: none;
	border-radius: 10px;
	padding: 1rem;
}

button:hover {
	cursor: pointer;
	opacity: .8;
}

.conditions {
	color:hsl(0, 100%, 74%);
	font-weight: 600;
}

.claim {
	background: hsl(154, 59%, 51%);
	text-transform: uppercase;
	font-weight: 700;
	box-shadow: 0 4px 0 0 hsl(154, 59%, 42%);
	width: 91.3%;
}

.content {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-top: 25vh;
}

.form-container {
	min-width: 500px;

}
.form-input {
	background: white;
	border-radius: 5px;
	box-shadow: 0 8px 0 0 rgba(0, 0, 0, 0.1);
	min-height: fit-content;
}

input:focus {
	border: 1px solid rgb(0, 0, 0);
	outline: none;
}
input {
	border-radius: 4px;
	border: 1px solid hsl(246, 25%, 77%); 
	padding: 1rem;
	width: 83%;
	font-weight: 600;
	font-family: 'Poppins';
}

.form-container, .heading {
    padding: 3rem;
}

.main-header {
    max-width: 420px;
    font-size: 3rem;
}


.main-header, .sub-header {
	color: white;
}

.message {
	min-height: 100px;
}

.sub-header {
	max-width: 500px;
}

.terms {
	color: hsl(246, 25%, 77%);
}

.trial {
	background: hsl(248, 32%, 49%);
	box-shadow: 0 4px 0 0 rgba(0, 0, 0, 0.2)
}


.t-c {
	display: flex;
	font-size: .7rem;
	justify-content: center;
	padding-bottom: 2rem;
	text-align: center;
}

@media only screen and (max-width: 1207px) {
	.content {
		padding-top: 0;
		transform: translateY(-2rem);
	}

	.form-container {
		transform: translateY(-5rem);
	}

	.heading {
		text-align: center;
	}


	.main-header {
		padding-left: 31.26px;
	}
}


@media only screen and (max-width: 620px) {
	
	.content {
		max-width: fit-content;
	}
	
	.form-container {
		min-width: 370px;
	}
	
	.form-input {
		border-radius: 15px;
	}
	
	.heading {
		min-width: fit-content;
	}
	
	.main-header {
		font-size: 2rem;
		padding-left: 0;
	}

	.sub-header {
		font-size: 1.2rem;
	}

	.trail {
		padding: 1.5rem 5rem 1.5rem 5rem;
		font-size: large;
	}

	.t-c {
		padding-left: 1rem;
		padding-right: 1rem;
	}

	.terms {
		width: 250px;
	}

	ul {
		transform: translateX(-1vw);
	}
}
</style>