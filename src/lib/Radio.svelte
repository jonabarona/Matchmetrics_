<script>
  // based on suggestions from:
  // Sami Keijonen https://webdesign.tutsplus.com/tutorials/how-to-make-custom-accessible-checkboxes-and-radio-buttons--cms-32074
  // and Inclusive Components by Heydon Pickering https://inclusive-components.design/toggle-button/

  export let options;
  export let legend;
  export let userSelected = options[0].value;
  export let fontSize = 16;
  export let flexDirection = "column";

  const uniqueID = Math.floor(Math.random() * 100);

  const slugify = (str = "") =>
    str.toLowerCase().replace(/ /g, "-").replace(/\./g, "");
</script>

<div
  role="radiogroup"
  class="group-container"
  aria-labelledby={`label-${uniqueID}`}
  style="font-size:{fontSize}px; flex-direction:{flexDirection}"
  id={`group-${uniqueID}`}
>
  <div class="legend" id={`label-${uniqueID}`}>{legend}</div>
  {#each options as { value, label }}
    <input
      class="sr-only"
      type="radio"
      id={slugify(label)}
      bind:group={userSelected}
      {value}
    />
    <label for={slugify(label)}> {label} </label>
  {/each}
</div>
