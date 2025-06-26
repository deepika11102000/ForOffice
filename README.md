<select id="incotermYear">
  <option value="">Select Year</option>
  <option value="2010">2010</option>
  <option value="2020">2020</option>
</select>

<select id="INCOTERMS" name="INCOTERMS" title="Incoterms" disabled>
  <option value="">Select Incoterm</option>
</select>

<script>
  // Define mapping of year => array of {value, text}
  const incotermOptions = {
    "2010": [
      { value: "1",  text: "EXW" },
      { value: "2",  text: "FCA" },
      { value: "3",  text: "FAS" },
      { value: "4",  text: "FOB" },
      { value: "5",  text: "CFR" },
      { value: "6",  text: "CIF" },
      { value: "7",  text: "CPT" },
      { value: "8",  text: "CIP" },
      { value: "13", text: "DDP" },
      { value: "16", text: "DAT" },
      { value: "17", text: "DAP" }
    ],
    "2020": [
      { value: "1",  text: "EXW" },
      { value: "2",  text: "FCA" },
      { value: "7",  text: "CPT" },
      { value: "18", text: "DPU" },
      { value: "17", text: "DAP" }
    ]
  };

  const yearEl = document.getElementById("incotermYear");
  const codeEl = document.getElementById("INCOTERMS");

  yearEl.addEventListener("change", () => {
    const selectedYear = yearEl.value;

    // Clear existing options
    codeEl.innerHTML = '<option value="">Select Incoterm</option>';

    if (incotermOptions[selectedYear]) {
      // Populate new options
      incotermOptions[selectedYear].forEach(optData => {
        const opt = document.createElement("option");
        opt.value = optData.value;
        opt.textContent = optData.text;
        codeEl.appendChild(opt);
      });
      codeEl.disabled = false;
    } else {
      codeEl.disabled = true;
    }
  });

  // *(Optional)* Initialize on page load if a year is pre-selected
  window.addEventListener("DOMContentLoaded", () => {
    if (yearEl.value) {
      yearEl.dispatchEvent(new Event('change'));
    }
  });
</script>
