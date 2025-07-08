const incotermMap = {
    '1': 'EXW',
    '2': 'FCA',
    '3': 'FAS',
    '4': 'FOB',
    '5': 'CFR',
    '6': 'CIF',
    '7': 'CPT',
    '8': 'CIP',
    '16': 'DAT',
    '17': 'DAP',
    '13': 'DDP',
    '18': 'DPU'
};

function modifyincoterm_change(){
    const selectedValue = document.getElementById("INCOTERMS").value;
    if (incotermMap[selectedValue]) {
        setFldvalue('INCOTERMS', incotermMap[selectedValue]);
    }
}

