ts is for running bad apple!! on almost every site as background (no sound)

code for tampermonkey:

    // ==UserScript==
    // @name         Bad Apple!! on every website
    // @description  bad maça
    // @version      69
    // @match        *://*/*
    // @grant        none
    // ==/UserScript==

    (function() {
        'use strict';

        const video = document.createElement('video');
        video.src = 'https://legustalo.github.io/videos/BadApple.webm';
        video.autoplay = true;
        video.loop = true;
        video.muted = true;
        video.playsInline = true;

        Object.assign(video.style, {
            position: 'fixed',
            top: '0',
            left: '0',
            width: '100vw',
            height: '100vh',
            objectFit: 'cover',
            zIndex: '-1',
            pointerEvents: 'none'
        });
    
        document.documentElement.appendChild(video);

        const style = document.createElement('style');
        style.innerHTML = `
            html, body {
                background: transparent !important;
            }
        `;
        document.head.appendChild(style);

    })();
