<script>
  import logo from "./assets/logopink2.png"
  import tape1 from "./assets/tape1.png"

  let audio;
  let paused = true;

  const togglePlay = () => {
    if (paused) {
      audio.play();
    }
    else {
      audio.pause();
    }
  }
</script>

<main>
<div class="center">
    <div class="player">
      <!-- frame -->
      <div id="f1" class="frame"></div>
      <div id="f2" class="frame"></div>
      <div id="f3" class="frame"></div>
      <div id="f4" class="frame"></div>

      <div id="f5" class="bg"></div>
      <div id="f6" class="bg"></div>
      <div id="f7" class="bg"></div>
      <div id="f8" class="bg"></div>

      <div id="e1" class="empty">
        <div id="rLeft" class={!paused ? "rotate" : ""}><img src={tape1} alt="Tape1"/></div>
        <div id="rRight" class={!paused ? "rotate" : ""}><img src={tape1} alt="Tape1"/></div>
      </div>

      <div id="e9" class="empty">
        <img src={logo} alt="Logo"/>
      </div>

      <!-- cassette -->
      <div id="c1" class="cassetteA"></div>
      <div id="c2" class="cassetteA"></div>
      <div id="c3" class="cassetteA"></div>
      <div id="c4" class="cassetteA"></div>

      <div id="c5" class="cassetteB"></div>
      <div id="c6" class="cassetteB"></div>
      <div id="c7" class="cassetteB"></div>
      <div id="c8" class="cassetteB"></div>

      <div id="c9" class="cassetteA"></div>
      <div id="c10" class="cassetteA"></div>
      <div id="c11" class="cassetteA"></div>
      <div id="c12" class="cassetteA"></div>

      <div id="c13" class="cassetteA"></div>
      <div id="c14" class="cassetteA"></div>
      <div id="c15" class="cassetteA"></div>
      <div id="c16" class="cassetteA"></div>

      <div id="c17" class="cassetteA"></div>
      <div id="c18" class="cassetteA"></div>
      <div id="c19" class="cassetteA"></div>
      <div id="c20" class="cassetteA"></div>

      <div id="c21" class="cassetteA"></div>
      <div id="c22" class="cassetteA"></div>
      <div id="c23" class="cassetteA"></div>
      <div id="c24" class="cassetteA"></div>

      <!-- label -->
        <div id="l2" class="labelB"></div>
        <div id="l3" class="labelA"></div>
        <div id="l1" class="labelA"></div>
        <div id="l4" class="labelC"></div>

      <!-- dots -->
      <div id="d1" class="bg"></div>
      <div id="d2" class="bg"></div>
      <div id="d3" class="bg"></div>
      <div id="d4" class="bg"></div>

      <div id="d5" class="labelA"></div>
      <div id="d6" class="bg"></div>
      <div id="d7" class="bg"></div>
      <div id="d8" class="labelB"></div>

      <!-- button -->
      <div role = "button" tabIndex={0} id="button" class={paused ? "buttonUp" : "buttonDown"} on:click={togglePlay}>
        <div class={paused ? "buttonUpIcon" : "buttonDownIcon" } />
        <audio
          bind:this={audio}
          bind:paused
          src={"https://radioadmin.kmn.lt:8443/main"}
        />
      </div>
    </div>
  </div>
</main>

<style type="text/scss">
$background: #202833;
$frame: #413440;
$empty: none;
$cassetteA: #fdb62f;
$cassetteB: #8c421c;
$labelA: #ff69b4;
$labelB: #ffff00;
$labelC: #718F8F;
$labelD: #5FF5F5;

.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  min-height: 90vh;
}

.player {
  display: grid;
  grid-template-columns: repeat(41, 15px);
  grid-template-rows: repeat(35, 15px);
}

.bg {
  background-color: $background;
}

.frame {
  background-color: $frame;
}

#f1 {
  grid-column-start: 1;
  grid-column-end: 42;
  grid-row-start: 1;
  grid-row-end: 4;
}

#f2 {
  grid-column-start: 39;
  grid-column-end: 42;
  grid-row-start: 1;
  grid-row-end: 36;
}

#f3 {
  grid-column-start: 4;
  grid-column-end: 39;
  grid-row-start: 27;
  grid-row-end: 36;
}

#f4 {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 4;
  grid-row-end: 36;
}

#f5 {
  grid-column-start: 4;
  grid-column-end: 38;
  grid-row-start: 4;
  grid-row-end: span 1;
}

#f6 {
  grid-column-start: 38;
  grid-column-end: span 1;
  grid-row-start: 5;
  grid-row-end: 27;
}

#f7 {
  grid-column-start: 5;
  grid-column-end: 37;
  grid-row-start: 25;
  grid-row-end: span 1;
}

#f8 {
  grid-column-start: 4;
  grid-column-end: span 1;
  grid-row-start: 4;
  grid-row-end: 26;
}

.empty {
  background-color: $empty;
}

#e1 {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  // align-items:;


  grid-column-start: 4;
  grid-column-end: 39;
  grid-row-start: 4;
  grid-row-end: span 27;

}

#rLeft {
  margin-top: 60px;
  height: 210px;
  width: 210px;
  z-index: -1;

  img {
    width: 100%;
  }
}

#rRight {
  margin-top: 60px;
  height: 210px;
  width: 210px;
  z-index: -1;

  img {
    width: 100%;
  }
}

#e9 {
  display: flex;
  // flex-direction: column;
  justify-content: center;
  align-items: center;

  grid-column-start: 15;
  grid-column-end: 28;
  grid-row-start: 12;
  grid-row-end: 18;

  img {
    padding-top: 5px;
    height: 100%;
  }
}

.rotate {
  animation: spin 2s linear infinite;
}

@-moz-keyframes spin { 100% { -moz-transform: rotate(360deg); } }
@-webkit-keyframes spin { 100% { -webkit-transform: rotate(360deg); } }
@keyframes spin { 100% { -webkit-transform: rotate(360deg); transform:rotate(360deg); } }

.cassetteA {
  background-color: $cassetteA;
}

.cassetteB {
  background-color: $cassetteB;
}

#c1 {
  grid-column-start: 5;
  grid-column-end: 38;
  grid-row-start: 5;
  grid-row-end: 12;
}

#c2 {
  grid-column-start: 34;
  grid-column-end: 38;
  grid-row-start: 12;
  grid-row-end: span 6;
}

#c3 {
  grid-column-start: 5;
  grid-column-end: 38;
  grid-row-start: 18;
  grid-row-end: 26;
}

#c4 {
  grid-column-start: 5;
  grid-column-end: 9;
  grid-row-start: 12;
  grid-row-end: span 6;
}

#c5 {
  grid-column-start: 12;
  grid-column-end: 31;
  grid-row-start: 21;
  grid-row-end: span 1;
}

#c6 {
  grid-column-start: 11;
  grid-column-end: 32;
  grid-row-start: 22;
  grid-row-end: span 1;
}

#c7 {
  grid-column-start: 10;
  grid-column-end: 33;
  grid-row-start: 23;
  grid-row-end: span 2;
}

#c8 {
  grid-column-start: 9;
  grid-column-end: 34;
  grid-row-start: 25;
  grid-row-end: span 1;
}

#c9 {
  grid-column-start: 7;
  grid-column-end: 15;
  grid-row-start: 12;
  grid-row-end: span 1;
}

#c10 {
  grid-column-start: 13;
  grid-column-end: span 2;
  grid-row-start: 13;
  grid-row-end: 19;
}

#c11 {
  grid-column-start: 9;
  grid-column-end: span 4;
  grid-row-start: 17;
  grid-row-end: span 2;
}

#c12 {
  grid-column-start: 8;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: 19;
}

#c13 {
  grid-column-start: 9;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: span 1;
}

#c14 {
  grid-column-start: 12;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: span 1;
}

#c15 {
  grid-column-start: 9;
  grid-column-end: span 1;
  grid-row-start: 16;
  grid-row-end: span 1;
}

#c16 {
  grid-column-start: 12;
  grid-column-end: span 1;
  grid-row-start: 16;
  grid-row-end: span 1;
}

#c17 {
  grid-column-start: 28;
  grid-column-end: 35;
  grid-row-start: 12;
  grid-row-end: span 1;
}

#c18 {
  grid-column-start: 34;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: 19;
}

#c19 {
  grid-column-start: 30;
  grid-column-end: span 4;
  grid-row-start: 17;
  grid-row-end: span 2;
}

#c20 {
  grid-column-start: 28;
  grid-column-end: span 2;
  grid-row-start: 13;
  grid-row-end: 19;
}

#c21 {
  grid-column-start: 30;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: span 1;
}

#c22 {
  grid-column-start: 33;
  grid-column-end: span 1;
  grid-row-start: 13;
  grid-row-end: span 1;
}

#c23 {
  grid-column-start: 30;
  grid-column-end: span 1;
  grid-row-start: 16;
  grid-row-end: span 1;
}

#c24 {
  grid-column-start: 33;
  grid-column-end: span 1;
  grid-row-start: 16;
  grid-row-end: span 1;
}

.labelA {
  background-color: $labelA;
}

.labelB {
  background-color: $labelB;
}

.labelC {
  background-color: $labelC;
}

.buttonUpIcon {
  width: 0; 
  height: 0; 
  border-top: 15px solid transparent;
  border-bottom: 15px solid transparent;
  border-left: 20px solid green;
}


.buttonDownIcon {
  width: 20px;
  height: 20px;
  background-color: $frame;
}

#l1 {
  grid-column-start: 8;
  grid-column-end: 35;
  grid-row-start: 7;
  grid-row-end: span 1;
}

#l2 {
  grid-column-start: 8;
  grid-column-end: 35;
  grid-row-start: 8;
  grid-row-end: span 2;
}

#l3 {
  grid-column-start: 8;
  grid-column-end: 35;
  grid-row-start: 10;
  grid-row-end: span 1;
}

#l4 {
  grid-column-start: 8;
  grid-column-end: 35;
  grid-row-start: 19;
  grid-row-end: span 2;
}

// dots


#d1 {
  grid-column-start: 6;
  grid-column-end: span 1;
  grid-row-start: 6;
  grid-row-end: span 1;
}

#d2 {
  grid-column-start: 36;
  grid-column-end: span 1;
  grid-row-start: 6;
  grid-row-end: span 1;
}

#d3 {
  grid-column-start: 6;
  grid-column-end: span 1;
  grid-row-start: 24;
  grid-row-end: span 1;
}

#d4 {
  grid-column-start: 36;
  grid-column-end: span 1;
  grid-row-start: 24;
  grid-row-end: span 1;
}

#d5 {
  grid-column-start: 15;
  grid-column-end: span 1;
  grid-row-start: 23;
  grid-row-end: span 1;
}

#d6 {
  grid-column-start: 28;
  grid-column-end: span 1;
  grid-row-start: 23;
  grid-row-end: span 1;
}

#d7 {
  grid-column-start: 12;
  grid-column-end: span 1;
  grid-row-start: 24;
  grid-row-end: span 1;
}

#d8 {
  grid-column-start: 30;
  grid-column-end: span 1;
  grid-row-start: 24;
  grid-row-end: span 1;
}

.buttonUp {
  background-color: $frame;
  box-shadow: 5px 6px #9e9e9e ;
  border: 1px solid $labelC;
}

.buttonDown {
  background-color: red;
  box-shadow: inset 0 0 10px #000000;
}

#button {
  cursor: pointer;

  
  grid-column-start: 16;
  grid-column-end: 26;
  grid-row-start: 29;
  grid-row-end: span 5;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;

  font-size: xx-large;

}

@media screen and (max-width: 615px) {
  .player {
    grid-template-columns: repeat(41, 8px);
    grid-template-rows: repeat(35, 8px);
  }

  #rLeft {
    margin-top: 32px;
    height: 112px;
    width: 112px;
  }

  #rRight {
    margin-top: 32px;
    height: 112px;
    width: 112px;
  }
}
</style>
