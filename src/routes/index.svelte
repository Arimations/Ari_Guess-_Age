<script>

    let name = "" ;
    let age = "" ;
    
    async function guessAge() {
      fetch('  https://api.agify.io/?name=' + name)
        .then((response) => response.json())
        .then((data) => {
          age = data.age; // Path for description
        });
    }
    
    </script>
    
    
    
    <h1>Guess Age</h1>
    
    <form on:submit|preventDefault={guessAge}>
        <label for="name">Name:</label>
        <input id="name" bind:value={name} type="text" />
        <button type="submit">Check</button>
    </form>

    
<p>Age: {age}</p>