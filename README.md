# page-obsidian-2
/* Modern Obsidian Aesthetics - Glassmorphism & Clean Header */

/* --- Typography & Headers --- */
.theme-dark,
.theme-light {
    --h1-gradient: linear-gradient(90deg, #7c3aed, #0d0d0d);
    --h2-color: #0d0d0d;
    --h3-color: #7c3aed;
    --link-color: #7c3aed;
}

/* H1 - En-tête de page Moderne (Style Journal/Clean) */
h1 {
    color: #0d0d0d !important;
    /* Texte noir/gris foncé solide */
    background: none !important;
    /* Pas de dégradé sur le texte */
    -webkit-text-fill-color: initial !important;
    font-weight: 700 !important;
    font-size: 2.2em !important;
    text-align: center;
    margin-bottom: 2rem !important;
    padding-bottom: 1rem;
    border-bottom: none !important;
    /* Plus de ligne sous le titre */
}

/* --- Encart Haut de Page (Style Moderne Soft "Vapeur") --- */
.markdown-preview-section::before,
.cm-content::before {
    content: "";
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 25vh;
    /* Hauteur de l'encart */

    /* Dégradé subtil Gris clair -> Transparent (comme l'image) */
    background: linear-gradient(180deg, #e3e3e3 0%, #f7f7f7 80%, rgba(255, 255, 255, 0) 100%);

    /* Effet "Glass" flouté */
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    z-index: 0;
    pointer-events: none;
    opacity: 1;
}

/* LAYOUT: Placer le titre DANS l'encart */

/* 1. Reset du padding haut */
.markdown-preview-section,
.cm-content {
    padding-top: 0 !important;
}

/* 2. Positionnement du Titre */
.markdown-preview-section h1,
.cm-content h1,
.inline-title {
    margin-top: 4vh !important;
    /* Titre descendu dans le gris */
    margin-bottom: 15vh !important;
    /* Marge pour pousser le texte APRES l'encart */
    position: relative;
    z-index: 2;
    text-align: center;
}

/* 3. Sécurité Z-Index */
.markdown-preview-section,
.cm-content,
.cm-scroller {
    position: relative;
    z-index: 1;
}

/* --- Autres Styles (H2, H3, etc) --- */

h2 {
    color: var(--h2-color) !important;
    font-weight: 700 !important;
    font-size: 1.8em !important;
    margin-top: 2rem !important;
    display: flex;
    align-items: center;
}

h2::before {
    content: '◈';
    margin-right: 10px;
    font-size: 0.8em;
    color: var(--h2-color);
    opacity: 0.8;
}

h3 {
    color: var(--h3-color) !important;
    font-weight: 600 !important;
    font-size: 1.4em !important;
    margin-top: 1.5rem !important;
    display: flex;
    align-items: center;
}

h3::before {
    content: '❖';
    margin-right: 8px;
    font-size: 0.8em;
    color: var(--h3-color);
    opacity: 0.8;
}

h4 {
    color: var(--text-muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-size: 0.85em !important;
    font-weight: 600 !important;
    margin-top: 1.5rem !important;
    border-bottom: 1px solid var(--background-modifier-border);
    padding-bottom: 0.5rem;
}

a.external-link {
    text-decoration: none;
    color: var(--link-color);
}

a.external-link::after {
    content: ' ↗';
    font-size: 0.8em;
    opacity: 0.7;
}

input[type="checkbox"] {
    -webkit-appearance: none;
    appearance: none;
    width: 1.1em;
    height: 1.1em;
    border: 1px solid var(--text-muted);
    border-radius: 50%;
    margin-right: 0.5em;
    position: relative;
    top: 2px;
    transition: all 0.2s ease;
    cursor: pointer;
}

input[type="checkbox"]:checked {
    background: var(--h2-color);
    border-color: var(--h2-color);
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='white' stroke-width='3' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='20 6 9 17 4 12'%3E%3C/polyline%3E%3C/svg%3E");
    background-size: 70%;
    background-position: center;
    background-repeat: no-repeat;
}

.callout {
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 12px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.callout:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

.callout[data-callout="note"] {
    background: linear-gradient(135deg, rgba(124, 58, 237, 0.1), rgba(229, 5, 5, 0.1));
    border-left-color: var(--h3-color);
}

.note-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.note-item {
    flex: 1 1 300px;
}
