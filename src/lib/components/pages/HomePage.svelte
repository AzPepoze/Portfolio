<script>
  import Page from "../Page.svelte";
</script>

<Page>
  <div class="LeftFrame">
    <div
      class="MainText StrokeText"
      style="animation: Typing 0.5s infinite; border-right: 5px solid;"
    >
      Hello!
    </div>
    <div class="SubText">First of all, Please choose your language.</div>
  </div>

  <div class="RightFrame">
    <div
      id="google_translate_element"
      class="google-translate-container"
    ></div>

    <div class="SubText CenterText">
      <br />You can scroll (Mouse), swipe (Touch screen)<br />and select page at
      bottom to change page.
    </div>
  </div>
</Page>
