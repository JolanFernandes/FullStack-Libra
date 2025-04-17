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
            <button type="button" on:click={convert_cel_to_f}>Cel to F</button>
          </li>
          <li>
            <button type="button" on:click={convert_km_to_m}>Km to M</button>
          </li>
        </ul>
      {/if}
    </div>
    <p>Output: {result}</p>
  </div>
</div>
