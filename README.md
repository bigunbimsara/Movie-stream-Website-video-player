# Movie-stream-Website-video-player
A sleek, responsive video player built with HTML, CSS, and JavaScript for seamless episode navigation. Features dynamic episode buttons, Google Drive video embedding, and a modern UI with hover effects and active state styling. Ideal for integrating into websites to showcase video content.



<div class="buttons" id="episode-buttons">
  <!--Episode buttons will be added here dynamically-->
</div>

<div class="video-wrapper">
  <iframe allowfullscreen="" id="video-frame" src="https://drive.google.com/file/d/1mpg7TdD1tRtG1LAhE8BlQR0kpxsY3sIh/preview"></iframe>
</div>

<style>
  .buttons {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 30px;
  }
  .ep-btn {
    background-color: #e50914;
    color: white;
    border: none;
    border-radius: 8px;
    padding: 10px 16px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.2s;
  }
  .ep-btn:hover {
    background-color: #b00610;
    transform: scale(1.05);
  }
  .ep-btn.active {
    background-color: #FFD700;
    color: #111;
    font-weight: bold;
  }
  .video-wrapper {
    position: relative;
    max-width: 800px;
    margin: 0 auto 40px;
    border-radius: 12px;
    overflow: hidden;
    background: linear-gradient(135deg, #5a001f, #2b0049);
    box-shadow: 0 0 40px rgba(255, 40, 40, 0.8);
  }
  .video-wrapper iframe {
    width: 100%;
    height: 450px;
    border: none;
    border-radius: 12px;
  }
</style>

<script>
  const videoLinks = [
    "1mpg7TdD1tRtG1LAhE8BlQR0kpxsY3sIh",
    "1FzLkTkMSVk4GsSt1AILrfMope_H9-Xr4",
    "1m8Kh5VbSiEjFWy6_Ox9C6FnNywVASO2G",
    "1gsActAZpfMchEObkfH0ff6XR9IyKv49h",
    "1FqgogVtmFVGDkvOjfynX0RAe2ms5WcFZ",
    "12kNogxY8V9hop2ji692VJsKFAuT1444i",
    "1WD8QYeVfHIfxrTGdnFdJZQBcykedyoIf",
    "1PVkkN8yt2-tD_fW97ldXfDhphfvjg4te",
    "1PMOfaI4PaVIHMdFgPfzLZDgKELsP1eP7",
    "1G1L5fe_wrw7hLEPh9nJ4zoX8izNlEdtq",
    "1dGbV-uAn01U_oZoGMrEOsFseVJ5Ja_yu",
    "1rwk4-hrMYQsPl3-vShq09-To00R-chVq",
    "1gEuHUTWmmgsk6nJUOLlmS_xPvm41zcbM",
    "1a0N8UX7bhG2f-pZxbJXuY_y02JJfl37p",
    "1TnzYVz693YHnYjIkkCp5JL5WGxCTKIHq",
    "1FTBhkg77iEBqmNL6lZOElHIDU38ZExjw",
    "1KkKnsDpizT9ZqCn6qtbu5PD9RON3a_C2",
    "1OgE-rH0qs5dIzCrnC6qx2NxntS2wzrFL",
    "1wqGNxcFIS-o6wH0nELnL3Nj-bFs-Uw1Z",
    "19WvsqAhHnYRHToaedXzVh8A7hfC9eBMf",
    "1mAfNoPdR2dudb08tsYd0wsDhWXb5k8f4",
    "1ee6jo3elcV9Eo-N5r-Tk4nAzU4uK1KkN",
    "12_VfYiFXlGdxnqhiN4_JPMigla631A3q",
    "1neLKYEr3ss8KVfVFCW0lKqiSxTf9BS42"
  ];

  const buttonsContainer = document.getElementById('episode-buttons');
  const iframe = document.getElementById('video-frame');

  videoLinks.forEach((id, index) => {
    const button = document.createElement('button');
    button.className = 'ep-btn';
    button.innerText = `EP ${index + 1}`;
    button.addEventListener('click', () => {
      iframe.src = `https://drive.google.com/file/d/${id}/preview`;

      document.querySelectorAll('.ep-btn').forEach(btn => btn.classList.remove('active'));
      button.classList.add('active');
    });

    if (index === 0) {
      button.classList.add('active');
    }

    buttonsContainer.appendChild(button);
  });
</script>
