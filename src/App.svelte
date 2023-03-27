<script>
import Header from "./UI/Header.svelte";
import Grid from "./Meets/Grid.svelte";
import TextInput from "./UI/TextInput.svelte";
import Button from "./UI/Button.svelte"


let title= "";
let subtitle ="";
 let imageUrl = "";
 let description = "";
 let city = "";
 let contactEmail= "";

let meetings = [
    {
        id: "meet1",
        title: "Coding Bootcamp",
        subtitle: "Learn to code",
        description: "Come and code",
        imageUrl: "https://camo.githubusercontent.com/4a4353b420dfe0c1cb7c3cae3bc24c799ec4b4f6914472888765b341bc2a176e/68747470733a2f2f7777772e6d65657475702e636f6d2f6d755f7374617469632f656e2d55532f6c6f676f2d2d7363726970742e30303461646130352e737667",
        city: "Madrid",
        contactEmail: "test@test.com"
    },
    {
         id: "meet2",
        title: "Dancing Bootcamp",
        subtitle: "Learn to dance",
        description: "Come and dance",
        imageUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRABNaakyeH19qSUV8uSJJK-cTGkMGgsa6CYA&usqp=CAU",
        city: "Lisbon",
        contactEmail: "test2@test.com"
    }

    
]

function addMeet() {
const newMeetings = {
    id: Math.random().toString(),
    title: title,
    subtitle: subtitle,
    description: description,
    imageUrl: imageUrl,
    city: city,
    contactEmail: contactEmail
};
meetings = [newMeetings, ...meetings]

}

</script>
<style>
    main {
        margin-top: 5rem;
    }
    form {
        width: 30rem;
        max-width: 90%;
        margin: auto;
    }
</style>


<Header />

<main>
    <form on:submit|preventDefault={addMeet}>
        <TextInput id="title" label="Title" type="text" value={title} on:input="{(event) => (title = event.target.value)}"/>
        <TextInput id="subtitle" label="Subtitle" type="text" value={subtitle} on:input="{(event) => (subtitle = event.target.value)}"/>
       <TextInput id="city" label="City" type="text" value={city} on:input="{(event) => (city = event.target.value)}"/>
        <TextInput id="imageUrl" label="Image URL" type="text" value={imageUrl} on:input="{(event) => (imageUrl = event.target.value)}"/>
        <TextInput id="email" label="E-mail" type="email" value={contactEmail} on:input="{(event) => (contactEmail = event.target.value)}"/>
        <TextInput id="description" label="Description" controlType="textarea" value={description} on:input="{(event) => (contactEmail = event.target.value)}"/>
        
       <Button type="submit" caption="Save"/>
     </form>
    <Grid {meetings} />

</main>
