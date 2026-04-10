---
layout: default
---

<p class="lead"><span class="needs-check">DiaryPlay assists everyday storytellers in creating interactive vignettes.</span></p>

<div class="button-row">
  <a class="button-link" href="/papers/CHI2026-DiaryPlay-CameraReady.pdf"><span class="needs-check">Paper PDF</span></a>
  <a class="button-link" href="https://doi.org/10.1145/3772318.3790572"><span class="needs-check">ACM DL</span></a>
  <a class="button-link secondary" href="#system-overview" target="_self"><span class="needs-check">System Overview</span></a>
  <a class="button-link secondary" href="#authoring-scenario" target="_self"><span class="needs-check">Authoring Steps</span></a>
  <a class="button-link secondary" href="#viewing-scenario" target="_self"><span class="needs-check">Viewing Steps</span></a>
  <a class="button-link secondary" href="#cd-module" target="_self"><span class="needs-check">CD Module</span></a>
  <a class="button-link secondary" href="#paper-links" target="_self"><span class="needs-check">Citation</span></a>
</div>

<div class="figure-frame">
  <img src="/assets/img/diaryplay-hero.png" alt="DiaryPlay teaser figure" />
</div>

<hr />

<div id="abstract"></div>
## Abstract

An interactive vignette is a visual storytelling medium that lets the audience role-play a character and interact with non-player characters (NPCs) and the digital environment. Yet, the authoring complexity of interactive vignettes has obstructed their adoption in everyday storytelling, which builds on immediacy. We introduce <span style="color:{{site.syscolor}}">DiaryPlay</span>, an AI-assisted authoring system that generates interactive vignettes from text stories. The Authoring Component visually elicits three core elements (environment, characters, events) through automation and author refinement. The Viewing Component delivers an interactive story to the audience using an LLM-powered Controlled Divergence Module, which allows divergent player and NPC behaviors within the boundaries defined by the author's intended story. A technical evaluation shows that the Controlled Divergence module generates believable NPC activities based on both character persona and storyline. A user study demonstrates that <span style="color:{{site.syscolor}}">DiaryPlay</span> enables low-effort authoring of interactive vignettes for everyday storytelling while providing engaging viewing experiences and conveying the core story message.

<div class="key-points">
  <div class="info-card">
    <h3>[DG1]</h3>
    <p>Enable a lightweight authoring process that matches the effort of everyday storytelling practices.</p>
  </div>
  <div class="info-card">
    <h3>[DG2]</h3>
    <p>Capture and convey the author's key message in the everyday story.</p>
  </div>
  <div class="info-card">
    <h3>[DG3]</h3>
    <p>Deliver an engaging viewing experience with situation-aware NPCs in a branching storyline.</p>
  </div>
</div>

<hr />

<div id="system-overview"></div>
## DiaryPlay System Overview

The Interactive Vignette Authoring Component takes the author's text story as input, extracts core elements (environment, characters, and events), and guides the author in refining them into structured interactive vignette elements. The Interactive Vignette Viewing Component enlivens NPCs and allows the player to control the PC, enabling an interactive narrative experience grounded in the authored storyline.

<div class="figure-frame">
  <img src="/assets/img/diaryplay-overview.png" alt="DiaryPlay system overview" />
</div>
<p class="figure-caption">Figure 3: DiaryPlay system overview.</p>

<hr />

<div id="authoring-scenario"></div>
## Steps in the Authoring Scenario

<p class="section-note center"><span class="needs-check">Select a step to reveal its corresponding description and figure.</span></p>

<div class="step-switcher" data-step-group="authoring">
  <div class="step-nav" role="tablist" aria-label="Authoring scenario steps">
    <button class="step-toggle is-active" type="button" role="tab" aria-selected="true" aria-controls="authoring-panel-1" data-step-target="authoring-1"><span class="needs-check">Step 1</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="authoring-panel-2" data-step-target="authoring-2"><span class="needs-check">Step 2</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="authoring-panel-3" data-step-target="authoring-3"><span class="needs-check">Step 3</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="authoring-panel-4" data-step-target="authoring-4"><span class="needs-check">Step 4</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="authoring-panel-5" data-step-target="authoring-5"><span class="needs-check">Step 5</span></button>
  </div>

  <div class="step-panel" id="authoring-panel-1" role="tabpanel" data-step-panel="authoring-1">
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 1</p>
      <h3><span class="needs-check">Input a story</span></h3>
      <div class="step-media">
        <img src="/assets/img/Astep1.png" alt="Authoring scenario step 1" />
      </div>
      <div class="step-copy-grid">
        <p>Kelly begins by entering an everyday story into the story input box: "My friend Julie helped me make a new Indonesian dish. We had dinner together. Then, Jack practiced his guitar while Julie sang a new song she had been practicing."</p>
        <p>Once the system processes the input, Kelly sees three panels displaying each of the initial extraction results of the three interactive vignette elements: environment, characters, and events.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="authoring-panel-2" role="tabpanel" data-step-panel="authoring-2" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 2</p>
      <h3><span class="needs-check">Label rooms</span></h3>
      <div class="step-media">
        <img src="/assets/img/Astep2.png" alt="Authoring scenario step 2" />
      </div>
      <div class="step-copy-grid">
        <p>Kelly decides to begin with the Environment panel, where she sees a home map layout with several empty pre-labeled rooms.</p>
        <p>She revises the "dining" label to "living room" to better align with her intended setup, then clicks the "Confirm the rooms" button to continue.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="authoring-panel-3" role="tabpanel" data-step-panel="authoring-3" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 3</p>
      <h3><span class="needs-check">Place objects</span></h3>
      <div class="step-media">
        <img src="/assets/img/Astep3.png" alt="Authoring scenario step 3" />
      </div>
      <div class="step-copy-grid">
        <p>Soon, she sees the rooms automatically populated by the system, including objects relevant to each room and objects required for the events in the story. To customize the environment, Kelly uses mouse drag-and-drop to reposition objects.</p>
        <p>Noticing that the living room feels crowded, she right-clicks to remove a carpet. She notices a chair is missing and then decides to add a dining chair in the kitchen, so she types "dining chair" in the input box above the map, clicks the "Generate" button, and places the new chair in her desired location.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="authoring-panel-4" role="tabpanel" data-step-panel="authoring-4" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 4</p>
      <h3><span class="needs-check">Complete the character profiles</span></h3>
      <div class="step-media">
        <img src="/assets/img/Astep4.png" alt="Authoring scenario step 4" />
      </div>
      <div class="step-copy-grid">
        <p>Kelly moves to the Character Panel. She notices three tabs, each representing a character from her input story: the Player Character, which will be controlled by the player, and two NPCs, her friends Julie and Jack.</p>
        <p>Each character tab includes an avatar selection and blank fields for defining persona. When filling in the persona fields, she struggles to articulate Jack's personality, so she uses the "Try to talk with this NPC" feature to simulate a real-life conversation she had with him. Once satisfied with the conversation sample, she clicks the "Suggestions" button and receives a suggestion bubble beneath the personality field.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="authoring-panel-5" role="tabpanel" data-step-panel="authoring-5" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 5</p>
      <h3><span class="needs-check">Refine the events with object assignment</span></h3>
      <div class="step-media">
        <img src="/assets/img/Astep5.png" alt="Authoring scenario step 5" />
      </div>
      <div class="step-copy-grid">
        <p>Kelly navigates to the Events panel, where she finds a visual timeline of key events, each containing character activities. She carefully reviews each event to verify that the system's extracted activities align with her input story.</p>
        <p>Kelly notices that an event generated from "We had dinner" included only Julie and her, but it should have included Jack too. To correct this, she clicks the add button and types "Having dinner" to add it to Jack's activities in the events panel. Next, to review and edit the target objects for each activity, she clicks on each activity, sees the system's automatic assignments, and opens the drop-down menu to select an object from the list.</p>
      </div>
    </div>
  </div>
</div>

<hr />

<div id="viewing-scenario"></div>
## Steps in the Viewing Scenario

<p class="section-note center"><span class="needs-check">Select a step to reveal its corresponding description and figure.</span></p>

<div class="step-switcher" data-step-group="viewing">
  <div class="step-nav" role="tablist" aria-label="Viewing scenario steps">
    <button class="step-toggle is-active" type="button" role="tab" aria-selected="true" aria-controls="viewing-panel-1" data-step-target="viewing-1"><span class="needs-check">Step 1</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="viewing-panel-2" data-step-target="viewing-2"><span class="needs-check">Step 2</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="viewing-panel-3" data-step-target="viewing-3"><span class="needs-check">Step 3</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="viewing-panel-4" data-step-target="viewing-4"><span class="needs-check">Step 4</span></button>
    <button class="step-toggle" type="button" role="tab" aria-selected="false" aria-controls="viewing-panel-5" data-step-target="viewing-5"><span class="needs-check">Step 5</span></button>
  </div>

  <div class="step-panel" id="viewing-panel-1" role="tabpanel" data-step-panel="viewing-1">
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 1</p>
      <h3><span class="needs-check">Read the caption</span></h3>
      <div class="step-media">
        <img src="/assets/img/Vstep1.png" alt="Viewing scenario step 1" />
      </div>
      <div class="step-copy-grid">
        <p>Bob starts by reading the text story as a caption to get an overview of the characters and events.</p>
        <p>He realizes that he will role-play as Kelly and interact with two other characters, Julie and Jack.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="viewing-panel-2" role="tabpanel" data-step-panel="viewing-2" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 2</p>
      <h3><span class="needs-check">Engage with the first key event</span></h3>
      <div class="step-media">
        <img src="/assets/img/Vstep2.png" alt="Viewing scenario step 2" />
      </div>
      <div class="step-copy-grid">
        <p>As the interactive vignette loads, Bob notices the kitchen stove top glowing, signaling that an activity is about to take place at the stove. To trigger the activity, he uses the arrow keys to move the PC toward it. Upon approaching, the activity starts.</p>
        <p>Bob sees the glow disappear, and a speech bubble appears under the PC's avatar to show the PC's activity: "Cooking dinner." Bob then observes Julie moving in the kitchen, and her speech bubble reads: "Helping with cooking."</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="viewing-panel-3" role="tabpanel" data-step-panel="viewing-3" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 3</p>
      <h3><span class="needs-check">Diverge from the key events</span></h3>
      <div class="step-media">
        <img src="/assets/img/Vstep3.png" alt="Viewing scenario step 3" />
      </div>
      <div class="step-copy-grid">
        <p>After the cooking event is done, Bob sees the chair glowing, signaling the transition to the next key event, having dinner. However, instead of moving the PC to the glowing chair immediately, Bob decides to explore the home environment further.</p>
        <p>He moves the PC to the storage room and triggers the activity "Cleaning the bookshelf" at the bookshelf. Bob realizes Jack and Julie are not abandoning the PC to have dinner without Kelly. Instead, Bob observes that Jack and Julie are doing other activities.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="viewing-panel-4" role="tabpanel" data-step-panel="viewing-4" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 4</p>
      <h3><span class="needs-check">Return to the main storyline</span></h3>
      <div class="step-media">
        <img src="/assets/img/Vstep4.png" alt="Viewing scenario step 4" />
      </div>
      <div class="step-copy-grid">
        <p>Following the inner voice and Jack's response, Bob decides to move the PC to the glowing dining chair.</p>
        <p>After the PC arrives at the dining chair, Bob sees Jack and Julie join the PC for dinner.</p>
      </div>
    </div>
  </div>

  <div class="step-panel" id="viewing-panel-5" role="tabpanel" data-step-panel="viewing-5" hidden>
    <div class="step-card step-panel-card">
      <p class="step-index needs-check">Step 5</p>
      <h3><span class="needs-check">Complete the interactive vignette experience</span></h3>
      <div class="step-media">
        <img src="/assets/img/Vstep5.png" alt="Viewing scenario step 5" />
      </div>
      <div class="step-copy-grid">
        <p>After the "Having dinner" event, Bob notices Jack and Julie moving to the music room to practice guitar and singing. With no more glowing objects in the environment, Bob realizes he is free to move the PC, interacting with the characters and objects in the environment.</p>
        <p>After Jack and Julie complete their guitar practice and singing, Bob sees the end screen, marking the conclusion of the experience.</p>
      </div>
    </div>
  </div>
</div>

<hr />

<div id="cd-module"></div>
## Controlled Divergence Module

During the interactive vignette play time, the Controlled Divergence (CD) Module automatically transforms the single-branch sequence of events in the specification into a branch-and-bottleneck narrative structure reacting to the player interactions. The purpose of the CD Module is to allow both the PC and the NPCs to freely take divergent activities, while being subtly guided to stay within the controlled boundaries defined by the storyline from the author. From the interactive vignette author's perspective, the CD Module offloads the manual effort of crafting a multi-branch narrative; from the player's perspective, the CD Module provides player agency within the viewing experience.

<div class="figure-frame">
  <img src="/assets/img/diaryplay-cd-module.png" alt="The CD Module plans NPC activities and reacts to PC activities in a two-stage loop" />
</div>
<p class="figure-caption">Figure 8: The CD Module plans NPC activities and reacts to PC activities in a two-stage loop.</p>

<hr />

## Example interactive vignettes created by participants from the user study

As illustrated in Figure 9, participants used DiaryPlay to express a wide variety of stories, spanning across various locations (e.g., office, library, museum, home, theater, shopping mall), characters (e.g., family members, friends, colleagues, strangers, classmates), and types of events (e.g., work day, school morning routine, museum visit). This demonstrates DiaryPlay's capability to support diverse expressions of everyday stories.

<div class="figure-frame">
  <img src="/assets/img/diaryplay-examples.png" alt="Example interactive vignettes created by participants from the user study" />
</div>
<p class="figure-caption">Figure 9: Example interactive vignettes created by participants from the user study. Minor grammatical errors in the original stories have been revised for illustration.</p>

<hr />

<div id="paper-links"></div>

<h2><span class="needs-check">Citation</span></h2>

<h3><span class="needs-check">BibTeX</span></h3>

```bibtex
@inproceedings{10.1145/3772318.3790572,
  author = {Xu, Jiangnan and Cha, Haeseul and Choi, Gosu and Lee, Gyu-cheol and Yoon, Yeo-Jin and Lee, Zucheul and Papangelis, Konstantinos and Kim, Dae Hyun and Kim, Juho},
  title = {DiaryPlay: AI-Assisted Creation of Interactive Story Vignettes for Everyday Storytelling},
  year = {2026},
  isbn = {979-8-4007-2278-3},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  url = {https://doi.org/10.1145/3772318.3790572},
  doi = {10.1145/3772318.3790572},
  booktitle = {Proceedings of the 2026 CHI Conference on Human Factors in Computing Systems},
  numpages = {21},
  location = {Barcelona, Spain},
  series = {CHI '26}
}
```

<hr />

<p class="logos">
  <a href="https://kixlab.org"><img src="/assets/img/kixlab_logo.png" alt="Logo of KIXLAB" /></a>
  <a href="https://kaist.ac.kr"><img src="/assets/img/kaist_logo.png" alt="Logo of KAIST" /></a>
</p>

<script>
  (function () {
    const groups = document.querySelectorAll("[data-step-group]");

    groups.forEach((group) => {
      const buttons = Array.from(group.querySelectorAll("[data-step-target]"));
      const panels = Array.from(group.querySelectorAll("[data-step-panel]"));

      const activate = (target) => {
        buttons.forEach((button) => {
          const isActive = button.dataset.stepTarget === target;
          button.classList.toggle("is-active", isActive);
          button.setAttribute("aria-selected", isActive ? "true" : "false");
        });

        panels.forEach((panel) => {
          panel.hidden = panel.dataset.stepPanel !== target;
        });
      };

      buttons.forEach((button) => {
        button.addEventListener("click", function () {
          activate(this.dataset.stepTarget);
        });
      });

      if (buttons.length > 0) {
        activate(buttons[0].dataset.stepTarget);
      }
    });
  })();
</script>
