# Inklings

<ul id="file-list"></ul>
<script>
  fetch("https://api.github.com/repos/nonjo/inklings/contents/")
    .then(response => response.json())
    .then(data => {
      let list = document.getElementById("file-list");
      data.forEach(file => {
        if (file.name.endsWith(".md") && file.name !== "index.md") {
          let li = document.createElement("li");
          let a = document.createElement("a");
          a.href = file.name;
          a.textContent = file.name.replace(".md", "").replace("-", " ");
          li.appendChild(a);
          list.appendChild(li);
        }
      });
    });
</script>
