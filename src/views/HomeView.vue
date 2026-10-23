<script setup>
import FacultyandStaff from "../FacultyandStaff.vue";
import ProgramsOfferedSection from "../ProgramsOfferedSection.vue";



</script>

<template>
  <div class="site-shell">
    <header class="site-header">
      <a
        class="brand"
        href="#home"
        aria-label="CCS home"
      >
        <img
          class="brand-mark"
          src="https://ccs.cpu.edu.ph/wp-content/uploads/2021/10/cropped-CCS-Logov-new.png"
          alt=""
        />
        <span class="brand-copy"
          ><strong>COLLEGE OF<br />COMPUTER STUDIES</strong
          ><small>CPU · ILOILO CITY</small></span
        >
      </a>

      <nav class="main-nav" aria-label="Main navigation">
        <a href="#programs">Programs</a>
        <a href="#story">Our story</a>
        <a href="#faculty">Faculty</a>
      </nav>
    </header>

    

      <ProgramsOfferedSection />

      <section id="story" class="dean-section">
        <div
          class="dean-image"
          role="img"
          aria-label="Ma. Christina A. Quijano, Dean of the College of Computer Studies"
        ></div>
        <div class="dean-copy">
          <p class="eyebrow light-eyebrow">
            <span></span> A note from our dean
          </p>
          <span class="quote-mark" aria-hidden="true">“</span>
          <blockquote>
            Every new class brings its own ideas, its own energy, and its own
            way of making our campus better.
          </blockquote>
          <p class="dean-message">
            At CCS, each student is unique enough to achieve whatever they want
            to reach for. We look forward to what you will contribute, in the
            classroom and beyond it.
          </p>
          <div class="dean-signature">
            <span class="signature-line"></span>
            <p>
              <strong>Ma. Christina A. Quijano, MSCS</strong
              ><small>DEAN, COLLEGE OF COMPUTER STUDIES</small>
            </p>
          </div>
        </div>
      </section>

      <FacultyandStaff />


      <section class="contact-section">
       
        <div class="contact-content">
          <p class="eyebrow light-eyebrow">
            <span></span> Your next chapter starts here
          </p>
          <h2>Let's make<br /><em>it matter.</em></h2>
          <a class="contact-link" href="mailto:ccssec@cpu.edu.ph"
            >ccssec@cpu.edu.ph <span aria-hidden="true">↗</span></a
          >
        </div>
        <div class="contact-detail">
          <span>COLLEGE OF COMPUTER STUDIES</span
          ><span
            >CENTRAL PHILIPPINE UNIVERSITY<br />JARO, ILOILO CITY,
            PHILIPPINES</span
          >
        </div>
      </section>
    

    <footer class="site-footer">
      <a class="brand footer-brand" href="#home"
        ><img
          class="brand-mark"
          src="https://ccs.cpu.edu.ph/wp-content/uploads/2021/10/cropped-CCS-Logov-new.png"
          alt=""
        /><span class="brand-copy"
          ><strong>COLLEGE OF<br />COMPUTER STUDIES</strong
          ><small>CPU · ILOILO CITY</small></span
        ></a
      >
      <p>Different people. One goal.</p>
      <div class="footer-links">
        <a href="https://cpu.edu.ph/" target="_blank" rel="noreferrer"
          >Central Philippine University ↗</a
        ><a href="mailto:ccssec@cpu.edu.ph">Email CCS ↗</a>
      </div>
      <small class="copyright">© 2026 COLLEGE OF COMPUTER STUDIES · CPU</small>
    </footer>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=DM+Sans:wght@400;500;600;700&family=Manrope:wght@400;500;600;700;800&display=swap");

:root {
  --paper: #ffffff;
  --ink: #171717;
  --muted: #686868;
  --red: #343434;
  --forest: #1b1b1b;
  --line: rgba(23, 23, 23, 0.18);
  --mono: "DM Mono", "Courier New", monospace;
  --display: "Manrope", "Trebuchet MS", sans-serif;
  --body: "DM Sans", "Trebuchet MS", sans-serif;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
  scroll-padding-top: 84px;
}
body {
  min-width: 320px;
  margin: 0;
  color: var(--ink);
  background: var(--paper);
  font-family: var(--body);
  font-size: 15px;
  -webkit-font-smoothing: antialiased;
}
body,
button,
a {
  font-family: var(--body);
}
button,
a {
  -webkit-tap-highlight-color: transparent;
}
a {
  color: inherit;
  text-decoration: none;
}
button {
  color: inherit;
}
.site-shell a[href],
.site-shell button:not(:disabled) {
  cursor: pointer;
}
.site-shell button:disabled {
  cursor: not-allowed;
}
::selection {
  color: white;
  background: var(--red);
}
.site-shell {
  overflow: hidden;
}
.site-header {
  position: relative;
  z-index: 10;
  height: 82px;
  padding: 0 max(48px, calc((100vw - 1320px) / 2));
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.brand {
  display: inline-flex;
  align-items: center;
  gap: 11px;
}
.brand-mark {
  width: 44px;
  height: 44px;
  display: block;
  padding: 0;
  object-fit: contain;
}
.brand-copy {
  display: grid;
  gap: 4px;
}
.brand-copy strong {
  font-family: var(--display);
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 0.035em;
  line-height: 1.15;
}
.brand-copy small {
  color: var(--muted);
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.09em;
}
.main-nav {
  display: flex;
  align-items: center;
  gap: 35px;
  font-size: 12px;
  font-weight: 600;
}
.main-nav > a {
  position: relative;
  padding: 9px 0;
}
.main-nav > a::after {
  position: absolute;
  right: 0;
  bottom: 3px;
  left: 0;
  height: 1px;
  content: "";
  background: var(--red);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.2s;
}
.main-nav > a:hover::after {
  transform: scaleX(1);
}
.menu-toggle {
  display: none;
}
.hero {
  position: relative;
  min-height: 610px;
  height: min(690px, calc(100svh - 82px));
  color: white;
  background: #343434;
  isolation: isolate;
}
.hero-photo,
.hero-wash {
  position: absolute;
  z-index: -1;
  inset: 0;
}
.hero-photo {
  background-position: center 42%;
  background-size: cover;
  animation: hero-arrive 1.1s ease-out both;
}
.hero-wash {
  background:
    linear-gradient(
      90deg,
      rgba(17, 25, 22, 0.88) 0%,
      rgba(17, 25, 22, 0.68) 41%,
      rgba(17, 25, 22, 0.05) 100%
    ),
    linear-gradient(0deg, rgba(13, 20, 17, 0.47), transparent 34%);
}
.hero-content {
  position: relative;
  width: min(1320px, calc(100% - 96px));
  height: 100%;
  margin: auto;
  padding-top: clamp(106px, 15vh, 160px);
  animation: text-arrive 0.65s 0.12s both;
}
.eyebrow {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 0 0 22px;
  color: var(--red);
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
.eyebrow > span {
  width: 19px;
  height: 1px;
  background: currentColor;
}
.light-eyebrow {
  color: #d0d0d0;
}
.hero h1,
.section-heading h2,
.news-heading h2,
.campus-heading h2,
.contact-content h2 {
  margin: 0;
  font-family: var(--display);
  font-size: clamp(60px, 7.2vw, 104px);
  font-weight: 600;
  letter-spacing: -0.075em;
  line-height: 0.97;
}
.hero h1 em,
.section-heading h2 em,
.news-heading h2 em,
.campus-heading h2 em,
.contact-content h2 em {
  color: #c9c9c9;
  font-weight: 500;
}
.hero-description {
  max-width: 390px;
  margin: 26px 0 28px;
  color: rgba(255, 255, 255, 0.82);
  font-size: 15px;
  line-height: 1.7;
}
.hero-link {
  display: inline-flex;
  align-items: center;
  gap: 24px;
  padding: 12px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.65);
  font-size: 12px;
  font-weight: 600;
  transition: gap 0.2s;
}
.hero-link:hover {
  gap: 33px;
}
.hero-link span {
  color: #d0d0d0;
  font-size: 17px;
}
.hero-caption {
  position: absolute;
  right: 48px;
  bottom: 25px;
  left: 48px;
  display: flex;
  justify-content: space-between;
  color: rgba(255, 255, 255, 0.7);
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.12em;
}
.hero-stamp {
  position: absolute;
  right: max(48px, calc((100vw - 1320px) / 2));
  bottom: 69px;
  width: 105px;
  height: 105px;
  display: flex;
  flex-wrap: wrap;
  align-content: center;
  justify-content: center;
  gap: 2px;
  border: 1px solid rgba(255, 255, 255, 0.65);
  border-radius: 50%;
  color: white;
  font-family: var(--mono);
  font-size: 10px;
  transform: rotate(-11deg);
}
.hero-stamp span:nth-child(2n) {
  color: #d0d0d0;
}
.hero-stamp small {
  width: 100%;
  margin-top: 5px;
  text-align: center;
  font-size: 6px;
  line-height: 1.3;
  letter-spacing: 0.12em;
}
.intro-band {
  min-height: 76px;
  padding: 20px 48px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  color: var(--paper);
  background: var(--forest);
}
.intro-band p {
  margin: 0;
  font-family: var(--display);
  font-size: 13px;
  font-weight: 500;
}
.intro-band span {
  color: #c8c8c8;
  font-size: 17px;
}
.section-pad {
  padding-right: max(48px, calc((100vw - 1240px) / 2));
  padding-left: max(48px, calc((100vw - 1240px) / 2));
}
.news-heading,
.campus-heading {
  display: flex;
  justify-content: space-between;
  align-items: end;
}
.news-heading .eyebrow,
.campus-heading .eyebrow {
  margin-bottom: 24px;
}
.news-heading h2,
.campus-heading h2 {
  font-size: clamp(49px, 5.8vw, 74px);
  line-height: 0.99;
}
.news-heading h2 em,
.campus-heading h2 em {
  color: var(--red);
}
.text-link {
  display: inline-flex;
  align-items: center;
  gap: 18px;
  font-size: 11px;
  font-weight: 700;
}
.text-link b {
  color: var(--red);
  font-size: 17px;
  transition: transform 0.2s;
}
.dean-section {
  min-height: 548px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  color: white;
  background: var(--forest);
}
.dean-image {
  min-height: 548px;
  background: url("https://ccs.cpu.edu.ph/wp-content/uploads/2021/11/quijano-e1637132499305.png")
    center 28% / cover;
}
.dean-copy {
  position: relative;
  max-width: 680px;
  padding: 84px max(50px, calc((100vw - 1240px) / 2)) 65px 8.5%;
}
.dean-copy .eyebrow {
  margin-bottom: 26px;
}
.quote-mark {
  position: absolute;
  top: 118px;
  right: 11%;
  color: rgba(220, 220, 220, 0.38);
  font-family: Georgia, serif;
  font-size: 100px;
  line-height: 1;
}
.dean-copy blockquote {
  position: relative;
  max-width: 540px;
  margin: 0;
  font-family: var(--display);
  font-size: clamp(27px, 3vw, 39px);
  font-weight: 500;
  letter-spacing: -0.055em;
  line-height: 1.26;
}
.dean-message {
  max-width: 430px;
  margin: 21px 0 30px;
  color: rgba(255, 255, 255, 0.7);
  font-size: 13px;
  line-height: 1.75;
}
.dean-signature {
  display: flex;
  align-items: center;
  gap: 14px;
}
.signature-line {
  width: 27px;
  height: 1px;
  background: #c8c8c8;
}
.dean-signature p {
  display: grid;
  gap: 5px;
  margin: 0;
}
.dean-signature strong {
  font-size: 11px;
  font-weight: 600;
}
.dean-signature small {
  color: #c8c8c8;
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.1em;
}
.news-section {
  padding-top: 119px;
  padding-bottom: 126px;
}
.news-heading {
  margin-bottom: 48px;
}
.all-news {
  margin-bottom: 8px;
  padding-bottom: 8px;
  border-bottom: 1px solid var(--line);
}
.news-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 25px;
}
.news-image {
  position: relative;
  height: 228px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  overflow: hidden;
  background-color: #d4d2c8;
  background-position: center;
  background-size: cover;
}
.news-image::after {
  position: absolute;
  inset: 0;
  content: "";
  background: rgba(16, 25, 20, 0.1);
  transition: background 0.2s;
}
.news-image:hover::after {
  background: rgba(16, 25, 20, 0.25);
}
.news-image > span,
.news-image > b {
  position: relative;
  z-index: 1;
  width: 34px;
  height: 34px;
  display: grid;
  place-items: center;
  color: var(--ink);
  background: var(--paper);
  font-family: var(--mono);
  font-size: 10px;
}
.news-image > b {
  font-family: var(--body);
  font-size: 16px;
  font-weight: 400;
}
.news-meta {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  margin: 17px 0 12px;
  color: var(--muted);
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.07em;
  text-transform: uppercase;
}
.news-meta span {
  color: var(--red);
}
.news-card h3 {
  max-width: 360px;
  margin: 0 0 10px;
  font-family: var(--display);
  font-size: 20px;
  font-weight: 700;
  letter-spacing: -0.04em;
  line-height: 1.25;
}
.news-card > p {
  max-width: 370px;
  margin: 0;
  color: var(--muted);
  font-size: 12px;
  line-height: 1.65;
}
.campus-section {
  padding-top: 100px;
  padding-bottom: 102px;
  color: white;
  background: #292929;
}
.campus-heading {
  padding-bottom: 43px;
}
.campus-heading h2 em {
  color: #d0d0d0;
}
.campus-heading > p {
  width: min(340px, 34%);
  margin: 0 0 4px;
  color: rgba(255, 255, 255, 0.64);
  font-size: 13px;
  line-height: 1.8;
}
.spaces-grid {
  display: grid;
  grid-template-columns: 1.05fr 0.85fr 1.1fr;
  gap: 8px;
  padding: 0 max(48px, calc((100vw - 1320px) / 2));
}
.space-image {
  position: relative;
  height: 290px;
  margin: 0;
  background-color: #48544c;
  background-position: center;
  background-size: cover;
}
.space-two {
  margin-top: 43px;
}
.space-three {
  margin-top: 16px;
}
.space-image::after {
  position: absolute;
  inset: 40% 0 0;
  content: "";
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.55));
}
.space-image figcaption {
  position: absolute;
  z-index: 1;
  right: 17px;
  bottom: 15px;
  left: 17px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: var(--display);
  font-size: 14px;
  font-weight: 600;
}
.space-image figcaption span {
  color: #d0d0d0;
  font-family: var(--body);
  font-size: 18px;
}
.contact-section {
  position: relative;
  min-height: 467px;
  padding: 78px max(48px, calc((100vw - 1240px) / 2)) 35px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
  color: white;
  background: #111111;
  isolation: isolate;
}
.contact-content {
  position: relative;
  z-index: 1;
}
.contact-content .eyebrow {
  color: #c9c9c9;
}
.contact-content h2 {
  font-size: clamp(60px, 7vw, 86px);
}
.contact-content h2 em {
  color: #c9c9c9;
}
.contact-link {
  position: absolute;
  left: min(53%, 620px);
  bottom: 11px;
  display: inline-flex;
  align-items: center;
  gap: 24px;
  padding-bottom: 8px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.6);
  font-family: var(--display);
  font-size: 18px;
}
.contact-link span {
  color: #c9c9c9;
  font-size: 17px;
  transition: transform 0.2s;
}
.contact-link:hover span {
  transform: translate(3px, -3px);
}
.contact-detail {
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: space-between;
  color: rgba(255, 255, 255, 0.75);
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.1em;
  line-height: 1.8;
}
.contact-orbit {
  position: absolute;
  z-index: -1;
  border: 1px solid rgba(255, 255, 255, 0.17);
  border-radius: 50%;
}
.orbit-one {
  top: -320px;
  right: 2%;
  width: 690px;
  height: 690px;
}
.orbit-two {
  top: -230px;
  right: 10%;
  width: 500px;
  height: 500px;
}
.site-footer {
  min-height: 138px;
  padding: 27px max(48px, calc((100vw - 1320px) / 2));
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  align-items: center;
  row-gap: 23px;
}
.footer-brand .brand-mark {
  width: 38px;
  height: 38px;
}
.site-footer > p {
  margin: 0;
  color: var(--muted);
  font-family: var(--display);
  font-size: 14px;
  font-weight: 600;
}
.footer-links {
  display: flex;
  justify-content: end;
  gap: 21px;
  font-size: 10px;
  font-weight: 600;
}
.footer-links a:hover {
  color: var(--red);
}
.copyright {
  grid-column: 1 / -1;
  padding-top: 13px;
  border-top: 1px solid var(--line);
  color: var(--muted);
  font-family: var(--mono);
  font-size: 8px;
  letter-spacing: 0.08em;
}
@keyframes hero-arrive {
  from {
    transform: scale(1.035);
    opacity: 0.7;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}
@keyframes text-arrive {
  from {
    transform: translateY(13px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@media (min-width: 1440px) {
  .hero {
    height: 690px;
  }
}
@media (max-width: 900px) {
  .site-header {
    padding-right: 28px;
    padding-left: 28px;
  }
  .hero-content {
    width: calc(100% - 56px);
  }
  .main-nav {
    gap: 20px;
  }
  .hero-stamp {
    right: 30px;
  }
  .intro-band {
    padding-right: 28px;
    padding-left: 28px;
    gap: 10px;
  }
  .intro-band p {
    font-size: 10px;
  }
  .section-pad {
    padding-right: 40px;
    padding-left: 40px;
  }
  .dean-copy {
    padding-right: 35px;
    padding-left: 45px;
  }
  .news-grid {
    gap: 17px;
  }
  .news-image {
    height: 180px;
  }
  .spaces-grid {
    padding-right: 28px;
    padding-left: 28px;
  }
  .space-image {
    height: 230px;
  }
  .contact-section {
    padding-right: 40px;
    padding-left: 40px;
  }
  .site-footer {
    padding-right: 28px;
    padding-left: 28px;
  }
}
@media (max-width: 640px) {
  html {
    scroll-padding-top: 108px;
  }
  .site-header {
    position: relative;
    height: auto;
    padding: 12px 19px 10px;
    flex-wrap: wrap;
    gap: 10px;
  }
  .brand {
    color: var(--ink);
  }
  .brand-mark {
    width: 40px;
    height: 40px;
  }
  .brand-copy strong {
    font-size: 9px;
  }
  .brand-copy small {
    color: var(--muted);
  }
  .main-nav {
    position: static;
    order: 1;
    flex-basis: 100%;
    justify-content: space-between;
    gap: 12px;
    padding-top: 9px;
    border-top: 1px solid var(--line);
    font-size: 11px;
    color: var(--ink);
  }
  .main-nav > a {
    padding: 2px 0;
    color: var(--ink);
  }
  .main-nav > a::after {
    display: none;
  }
  .hero {
    min-height: 600px;
    height: 88svh;
    max-height: 720px;
  }
  .hero-photo {
    background-position: 58% center;
  }
  .hero-wash {
    background:
      linear-gradient(90deg, rgba(17, 25, 22, 0.84), rgba(17, 25, 22, 0.3)),
      linear-gradient(0deg, rgba(13, 20, 17, 0.48), transparent 38%);
  }
  .hero-content {
    width: calc(100% - 42px);
    padding-top: 125px;
  }
  .hero h1 {
    font-size: clamp(61px, 15vw, 88px);
  }
  .hero-description {
    max-width: 315px;
    font-size: 13px;
  }
  .hero-stamp {
    right: 20px;
    bottom: 67px;
    width: 76px;
    height: 76px;
    font-size: 8px;
  }
  .hero-stamp small {
    font-size: 5px;
  }
  .hero-caption {
    right: 20px;
    bottom: 17px;
    left: 20px;
    font-size: 6px;
  }
  .intro-band {
    padding: 19px 21px;
    display: grid;
    grid-template-columns: 1fr 15px 1fr;
    gap: 15px 8px;
  }
  .intro-band p {
    font-size: 10px;
  }
  .intro-band span {
    font-size: 12px;
  }
  .intro-band p:last-child {
    grid-column: 1 / -1;
  }
  .section-pad {
    padding-right: 21px;
    padding-left: 21px;
  }
  .news-heading,
  .campus-heading {
    align-items: flex-start;
    flex-direction: column;
    gap: 23px;
  }
  .news-heading h2,
  .campus-heading h2 {
    font-size: 55px;
  }
  .text-link {
    gap: 9px;
    font-size: 10px;
  }
  .dean-section {
    grid-template-columns: 1fr;
  }
  .dean-image {
    min-height: 320px;
    background-position: center 40%;
  }
  .dean-copy {
    padding: 49px 24px 55px;
  }
  .dean-copy blockquote {
    max-width: 470px;
    font-size: 32px;
  }
  .quote-mark {
    top: 90px;
    right: 12%;
    font-size: 75px;
  }
  .news-section {
    padding-top: 82px;
    padding-bottom: 82px;
  }
  .news-heading {
    margin-bottom: 33px;
  }
  .all-news {
    margin-top: -8px;
  }
  .news-grid {
    grid-template-columns: 1fr;
    gap: 31px;
  }
  .news-image {
    height: min(64vw, 290px);
  }
  .news-card h3 {
    font-size: 20px;
  }
  .campus-section {
    padding-top: 79px;
    padding-bottom: 75px;
  }
  .campus-heading {
    padding-bottom: 31px;
  }
  .campus-heading > p {
    width: 100%;
    max-width: 360px;
    font-size: 12px;
  }
  .spaces-grid {
    grid-template-columns: 1fr 1fr;
    gap: 7px;
    padding: 0 15px;
  }
  .space-image {
    height: 205px;
  }
  .space-two {
    margin-top: 22px;
  }
  .space-three {
    grid-column: 1 / -1;
    height: 220px;
    margin-top: -14px;
  }
  .contact-section {
    min-height: 423px;
    padding: 63px 22px 25px;
  }
  .contact-content h2 {
    font-size: 68px;
  }
  .contact-link {
    position: static;
    margin-top: 29px;
    font-size: 16px;
  }
  .contact-detail {
    font-size: 7px;
  }
  .orbit-one {
    top: -120px;
    right: -240px;
    width: 500px;
    height: 500px;
  }
  .orbit-two {
    top: -60px;
    right: -190px;
    width: 370px;
    height: 370px;
  }
  .site-footer {
    padding: 24px 20px;
    grid-template-columns: 1fr auto;
    row-gap: 18px;
  }
  .site-footer > p {
    grid-column: 1 / -1;
    grid-row: 2;
    font-size: 12px;
  }
  .footer-links {
    grid-column: 1 / -1;
    grid-row: 3;
    justify-content: flex-start;
    gap: 18px;
  }
  .copyright {
    grid-row: 4;
  }
}
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
</style>
