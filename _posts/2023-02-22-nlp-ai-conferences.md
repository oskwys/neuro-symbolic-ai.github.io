---
layout: post
title:  "NLP and AI Conferences and Journals"
date:   2023-02-22 17:00:00 +0000
categories: Resources
tags: Starter Conferences Journals
---

<script lang="javascript">
    function fill_table(tblId, data) {
        data.forEach(function (conf) {
            if (conf.deadline == "") {
                conf.deadline = String((new Date()).getFullYear() + 2);
            }
        });
        
        var conf_table = document.getElementById(tblId);
        evts_sorted = data.sort(function(a, b) {return (new Date(a.deadline) - new Date(b.deadline))});
        evts_sorted.forEach(function (evt) {
            if (evt.template != "") {
                deadline = new Date(evt.deadline);
                var row = document.createElement("tr");
                var col_name = document.createElement("td");
                col_name.style.textAlign = "left";
                col_name.innerHTML = "<a href=\"" + evt.url + "\">" + evt.name + "</a>";

                var col_deadline = document.createElement("td");
                col_deadline.style.textAlign = "center";
                if ((deadline.getTime() - (new Date()).getTime()) / (1000 * 3600 * 24) < 30)
                    col_deadline.style.color = "#CC0000";

                if (evt.deadline == String((new Date()).getFullYear() + 2))
                    col_deadline.innerHTML = "--";
                else
                    col_deadline.innerHTML = deadline.toLocaleDateString("en-UK");

                var col_template = document.createElement("td");
                col_template.style.textAlign = "center";
                col_template.innerHTML = "<a href=\"" + evt.template + "\">LaTeX</a>";

                row.appendChild(col_name);
                row.appendChild(col_deadline);
                row.appendChild(col_template);
                conf_table.appendChild(row);
            }
            
        });


    }

    async function load_conferences() {
        fetch("/assets/kb/conferences.json")
        .then(response => response.json())
        .then(data => fill_table("tblConferences", data))
        .catch(function(err){console.log(err);});
    }

    async function load_journals() {
        fetch("/assets/kb/journals.json")
        .then(response => response.json())
        .then(data => fill_table("tblJournals", data))
        .catch(function(err){console.log(err);});
    }

    document.addEventListener("DOMContentLoaded", function() {
        load_conferences();
        load_journals();
    });
</script>

<p style="font-size: 16pt;"> 
    This is a non-exhaustive list of important conferences and journals that you may want to submit your papers to, ordered by the closest deadline. Use the provided submission template and create your code repository based on the <a href="/kb.html#h-Publications" style="color: darkslateblue;">examples</a>.<br/>
    Deadlines closer than a month are marked in <span style="color: #CC0000;">red</span>.
</p>

## Conferences

<table>
  <thead>
    <tr>
      <th style="text-align: left">Conference</th>
      <th style="text-align: center; min-width: 100px;">Deadline</th>
      <th style="text-align: center">Submission template</th>
    </tr>
  </thead>
  <tbody id="tblConferences">
  </tbody>
</table>


## Journals

<table>
  <thead>
    <tr>
      <th style="text-align: left">Journal</th>
      <th style="text-align: center; min-width: 100px;">Deadline</th>
      <th style="text-align: center">Submission template</th>
    </tr>
  </thead>
  <tbody id="tblJournals">
  </tbody>
</table>
