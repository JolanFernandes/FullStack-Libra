<script>
  let standardInput;
  var result;
  let selected = "";
  let isOpen = false;
  function convert_lbs_to_kg() {
    const val = parseFloat(standardInput.value);
    if (!isNaN(val)) {
      result = val * 0.4535 + " Kg";
    } else {
      result = "Invalid input";
    }
  }

  function convert_cel_to_f() {
    const val = parseFloat(standardInput.value);
    if (!isNaN(val)) {
      result = val * 1.8 + 32 + " F";
    } else {
      result = "Invalid input";
    }
  }

  function convert_km_to_m() {
    const val = parseFloat(standardInput.value);
    if (!isNaN(val)) {
      result = val * 1000 + " Mtrs";
    } else {
      result = "Invalid input";
    }
  }
</script>

<h1>CALCULATOR</h1>
<div class="Calc_Body">
  <div class="Calc_Input">
    <p>Click below to enter</p>
    <input bind:this={standardInput} placeholder="Enter any number" /><br />
    <p>Select a Unit to convert</p>
    <div class="dropdown">
      <button on:click={() => (isOpen = !isOpen)}>
        Select Conversion {isOpen ? "▲" : "▼"}
      </button>
      {#if isOpen}
        <ul>
          <li>
            <button type="button" on:click={convert_lbs_to_kg}
              >Lbs to kgs</button
            >
          </li>
          <li>
            <button type="button" on:click={convert_cel_to_f}
              >Celsius to Farenheit</button
            >
          </li>
          <li>
            <button type="button" on:click={convert_km_to_m}
              >Kilometers to Meters</button
            >
          </li>
        </ul>
      {/if}
    </div>
    <p>Output: {result}</p>
  </div>
</div>

<style>
  /* Container styling */
  .Calc_Body {
    max-width: 400px;
    margin: 2rem auto;
    padding: 1.5rem;
    background-color: #f9f9f9; /* Light gray background */
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05); /* Subtle shadow */
    font-family: sans-serif;
  }

  /* Heading styling */
  h1 {
    text-align: center;
    margin-bottom: 1rem;
    font-size: 1.5rem;
    color: #333; /* Dark gray text */
  }

  /* Input section styling */
  .Calc_Input p {
    margin: 0.5rem 0;
    color: #555; /* Medium gray text */
  }

  .Calc_Input input {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #ccc; /* Light gray border */
    border-radius: 4px;
    font-size: 1rem;
    margin-bottom: 1rem;
  }

  /* Dropdown styling */
  .dropdown {
    position: relative;
  }

  .dropdown button {
    width: 100%;
    padding: 0.5rem;
    background-color: #007bff; /* Bootstrap primary blue */
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 1rem;
    cursor: pointer;
  }

  .dropdown ul {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    margin-top: 0.5rem;
    padding: 0;
    list-style: none;
    background-color: white;
    border: 1px solid #ccc; /* Light gray border */
    border-radius: 4px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05); /* Subtle shadow */
    z-index: 10;
  }

  .dropdown li button {
    width: 100%;
    padding: 0.5rem;
    background: none;
    border: none;
    text-align: left;
    font-size: 1rem;
    color: #333; /* Dark gray text */
    cursor: pointer;
  }

  .dropdown li button:hover {
    background-color: #f0f0f0; /* Light hover effect */
  }

  /* Output styling */
  .Calc_Input p:last-child {
    margin-top: 1rem;
    font-weight: bold;
    color: #333; /* Dark gray text */
  }
</style>
