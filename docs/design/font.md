# Polices d'écriture

Les polices d'écriture sont utilisées pour les titres, les sous-titres et les textes courants. Elles contribuent à définir l'identité visuelle de l'application et à faciliter la lecture des utilisateurs.

<div class="font_preview">
  <p class="font_preview_title fixel_text">
    Fixel Text
  </p>
  <p class="font_preview_sub fixel_text">
    Quand jadis, mon vaillant zéphyr explorait les cieux, papillon exquis, s'éveillant aux délices du jardin éternel, le parfum suave annonçait mille bonheurs.
  </p>
  <div class="font_bottom">
    <p class="font_preview_exp">
      Interface utilisateur
    </p>
    <a href="https://fixel.macpaw.com/" class="font_download">
      Télécharger
    </a>
  </div>
</div>

<div class="font_preview">
  <p class="font_preview_title onest">
    Onest
  </p>
  <p class="font_preview_sub onest">
    Quand jadis, mon vaillant zéphyr explorait les cieux, papillon exquis, s'éveillant aux délices du jardin éternel, le parfum suave annonçait mille bonheurs.
  </p>
  <div class="font_bottom">
    <p class="font_preview_exp">
      Communication visuelle
    </p>
    <a href="https://fonts.google.com/specimen/Onest" class="font_download">
      Télécharger
    </a>
  </div>
</div>

<style>
  @import url('https://fonts.macpaw.com/css?family=FixelText:400;500;600');
  @import url('https://fonts.googleapis.com/css2?family=Onest:wght@500..800&display=swap');

  .fixel_text {
    font-family: 'FixelText', sans-serif;
  }

  .onest {
    font-family: 'Onest', sans-serif;
  }

  .font_preview {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    padding: 1.2em;
    border-radius: 8px;
    background-color: var(--md-default-fg-color--lightest);
    border: 1px solid var(--md-default-fg-color--lighter);
    margin-bottom: 1em;
  }

  .font_preview * {
    margin: 0;
  }

  .font_preview_title {
    font-size: 1.4em;
    font-weight: 600;
  }

  .font_preview_sub {
    font-size: 1em;
    font-weight: 500;
    opacity: 0.8;
  }

  .font_bottom {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    margin-top: 1em;
    padding-top: 1em;
    border-top: 1px solid var(--md-default-fg-color--lighter);
  }

  .font_preview_exp {
    font-size: 0.9em;
    font-weight: 600;
    opacity: 0.8;
  }

  .font_download {
    font-size: 1em;
    font-weight: 500;
    text-decoration: none;
    color: var(--md-link-color);
  }
</style>