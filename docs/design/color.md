# Couleurs

Les couleurs forment la base de l'identité visuelle de l'application. Elles sont utilisées pour donner une identité visuelle à l'application et pour faciliter la lecture des utilisateurs.

## Les couleurs de la marque

### Couleurs principales

Les couleurs principales sont utilisées pour les éléments visuels importants de l'identité de marque. Elles sont utilisées pour les éléments visuels importants de l'application et de communication.

<div class="cards">
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #2A937A"
    ></div>
    <h3>Vert Papillon</h3>
    <p>#2A937A</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #32AB8E"
    ></div>
    <h3>Vert secondaire</h3>
    <p>#32AB8E</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #0DFF8B"
    ></div>
    <h3>Néon</h3>
    <p>#0DFF8B</p>
  </div>
</div>

### Couleurs secondaires

Les couleurs secondaires sont utilisées pour identifier et démarquer des élements précis de l'interface utilisateur ou de la communication, afin de créer des variations.

<div class="cards">
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #565EA3"
    ></div>
    <h3>Indigo</h3>
    <p>#565EA3</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #2E4277"
    ></div>
    <h3>Minuit</h3>
    <p>#2E4277</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #B18619"
    ></div>
    <h3>Moutarde</h3>
    <p>#B18619</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #B42828"
    ></div>
    <h3>Bordeaux</h3>
    <p>#B42828</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #A84700"
    ></div>
    <h3>Corail</h3>
    <p>#A84700</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #0065A8"
    ></div>
    <h3>Bleu</h3>
    <p>#0065A8</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #77FFFF"
    ></div>
    <h3>Cyan</h3>
    <p>#77FFFF</p>
  </div>
</div>

## Les couleurs de l'interface utilisateur

Sur Android, les couleurs utilisent le système Material You pour s'adapter à la couleur principale du fond d'écran de l'utilisateur. Sur iOS, les couleurs utilisent le système de couleurs par défaut.

!!! note warning "Utilisation d'élements visuels sur les fonds monochromes"
    **Lors d'utilisation d'élements sans ombres, les élements "cartes" doivent avoir une couleur de fond primaire et le fond de la vue doit être de couleur secondaire.** (ou alors une bordure légère doit être appliquée pour mettre en valeur le contenu)

### Thème clair

<div class="cards">
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #FFFFFF"
    ></div>
    <h3>Fond primaire</h3>
    <p>#FFFFFF</p>
    <p>UIColors.background</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #F3F2F8"
    ></div>
    <h3>Fond secondaire</h3>
    <p>#F3F2F8</p>
    <p>UIColors.modalBackground</p>
  </div>
</div>

### Thème sombre

<div class="cards">
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #0B0B0C"
    ></div>
    <h3>Fond primaire</h3>
    <p>#0B0B0C</p>
    <p>UIColors.background</p>
  </div>
  <div class="card">
    <div
      class="color_preview"
      style="background-color: #161618"
    ></div>
    <h3>Fond secondaire</h3>
    <p>#161618</p>
    <p>UIColors.modalBackground</p>
  </div>
</div>

<style>
  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
  }

  .card {
    display: flex;
    flex-direction: column;
    gap: 0px;
    padding: 0px;
    border-radius: 8px;

    background-color: var(--md-admonition-bg-color);
    border: 1px solid var(--md-default-fg-color--lighter);

    text-decoration: none;
    color: var(--md-default-fg-color);

    overflow: hidden;

    box-shadow: 0px 1px 3px #00000055;
  }

  .card:hover {
    box-shadow: 0px 2px 6px #00000055;
    transform: translateY(-2px);
  }

  .card * {
    margin: 0;
    padding: 0;
    text-decoration: none;
    color: var(--md-default-fg-color);
  }

  .card .color_preview {
    padding: 10px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #fff;
    font-size: 40px;
  }

  .card h3 {
    font-size: 1.1em;
    font-weight: bold;
    text-align: left;
    margin: 12px 12px;
    padding: 0;
    margin-bottom: 8px;
  }

  .card p {
    font-size: 0.85em;
    opacity: 0.8;
    text-align: left;
    margin: 0 12px;
    padding: 0;
    margin-bottom: 12px;
  }
</style>