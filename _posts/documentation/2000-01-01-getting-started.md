---
layout: post
title: Getting Started
category: documentation
---

Beta version of my upcoming Traffic Light Replacer mod

This mod allows for easy customization of your city's traffic lights. 

# Installation

1. [Subscribe](tba) to the mod on the Steam Workshop
1. Subscribe to supported pack(s)
1. Enable mod in Content Manager> Mods

# Supported Packs

No traffic lights are included with this mod; instead subscribe to one or more of the prop packs/mods below

<script>
var sheetUrl = 'https://spreadsheets.google.com/feeds/cells/1aBT0b0r-pOzU6AC3yI1C5exTcN2vtpTqJTNxTWYpYuc/1/public/full?alt=json';
  
  getData();
  async function getData(){
  const response = await fetch (sheetUrl);
  const data = await response.json();
  var table = data.feed.entry;
  console.log(table);
  var title = []; // the leftmost column of the Google Sheets
  var isSize = []; // second-left column
  var weblink = []; // second-left column
  var applink = []; // third-left column
  for (var i = 0; i < table.length; i += 5){
          // entry[i].content.$t retrieves the content of each cell
          title.push(table[i].content.$t);
          isSize.push(table[i+1].content.$t);
          weblink.push(table[i+3].content.$t);
          applink.push(table[i+4].content.$t);
        }
  
        console.log(title)
        console.log(weblink)
        console.log(isSize);
  
        //document.getElementById("data-display").innerHTML = "<p> Hello" + title[2] + "</p>";

        for (var i = 0; i<table.length/5; i++){
document.getElementById("data-display").innerHTML += `<div class="pure-u-1-2"><p>` + title[i] + `</p></div>`;
document.getElementById("data-display").innerHTML += `<div class="pure-u-1-6"><p>` + isSize[i] + `</p></div>`;
document.getElementById("data-display").innerHTML += `<div class="pure-u-1-6"><p><a href="` + weblink[i] + `">View Listing</a></p></div>`;
document.getElementById("data-display").innerHTML += `<div class="pure-u-1-6"><p><a href="` + applink[i] + `">Open in Steam</a></p></div>`;
        }
        
  }

</script>

   <div id="data-display">
  <div class="pure-u-1-2"><p>Pack Name</p></div>
  <div class="pure-u-1-6"><p>Multisize?</p></div>
</div>


Individual traffic light mods (ie. American Traffic Lights) need to be left disabled, otherwise conflicts will happen. The mod automatically disables individual traffic light mods on game startup since it only uses the bundled props.
