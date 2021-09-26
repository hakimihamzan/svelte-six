<script>
  // let name = "Mishima";
  let belt = "black";
  let firstName = "Yoshi";
  let lastName = "Nori";

  // reactive values -- updated DOM when value changed
  $: fullName = `${firstName} ${lastName}`;
  // reactive statement -- it wtach over the values used and if change statements will be executed
  $: {
    console.log(fullName);
    console.log(belt);
  }

  const handleClick = () => {
    if (belt == "black") {
      belt = "orange";
    } else {
      belt = "black";
    }
  };
  const handleInput = (e) => {
    belt = e.target.value;
  };
</script>

<main>
  <!-- <h1>Hello {name}!</h1> -->
  <!-- <button on:click={handleClick}>update belt colour</button> -->
  <!-- two way binding  with one way plus one way-->
  <!-- <input on:input={handleInput} type="text" value={belt}> -->
  <!-- binding the style here with the value of belt -->
  <p>{fullName}</p>
  <p style="color:{belt}">belt Colour {belt}</p>
  <!-- shorthand two way binding  -->
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" bind:value={belt} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  /* h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  } */

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
