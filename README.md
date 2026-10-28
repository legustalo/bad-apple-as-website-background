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
        video.src = 'https://legustalo.github.io/bad-apple-as-website-background/videos/BadApple.webm';
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

how it works:
"*://*/*"   * means that any character is accepted
the first is for protocol, second one is website and the third is for website path

uses a optimized webm video hosted at github pages and should run at every browser without consuming that much power and no need of specialp ermissions

i did not tested it yet, but it should be compatible at mobile with tampermonkey extension. but i think that in a 9:16 screen it would have a super zoom because i've set to COVER the screen and not CONTAIN. as said, not tested yet.

it replaces the website background at \<body\> and \<html\> by making it transparent and creates it

aspect ratio is 16:9, although it should've been 4:3; the video will pause if you leave the browser tab and will continue upon return

there is no way to interact and hear at all
