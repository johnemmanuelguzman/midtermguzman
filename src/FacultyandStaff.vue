<script setup>
import { computed, ref } from "vue";

const activeFilter = ref("All people");

const filters = ["All people", "Academic", "Staff"];
const portraitBase = "https://ccs.cpu.edu.ph/wp-content/uploads/2021/11/";

const people = [
  {
    name: "Ma. Christina A. Quijano, MSCS",
    role: "Dean",
    group: "Academic",
    photo: "quijano-e1637132499305.png",
  },
  {
    name: "Rea P. Balontong, MBA",
    role: "Department Head, IT & IS",
    group: "Academic",
    photo: "balontong-754x1024.jpg",
  },
  {
    name: "Marjee Rose B. Parreño, MSCS, MBA",
    role: "Program Coordinator, BSCS, BSDMIA & MSCS",
    group: "Academic",
    photo: "parreno-754x1024.jpg",
  },
  {
    name: "Ana Mae B. Cantel, MLIS",
    role: "Program Coordinator, BLIS & MLIS",
    group: "Academic",
    photo: "cantel-754x1024.jpg",
  },
  {
    name: "Lennon D. Pajar",
    role: "Computer Laboratory Coordinator",
    group: "Academic",
    photo: "pajar-754x1024.jpg",
  },
  {
    name: "Leo Paulo B. Beldia",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "beldia-754x1024.jpg",
  },
  {
    name: "Pedro Peter Rhys B. Cambronero, MSCS",
    role: "BSCS Program",
    group: "Academic",
    photo: "cambronero-754x1024.jpg",
  },
  {
    name: "Lesley Joy L. Dignadice, MBA",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "dignadice-1-754x1024.jpg",
  },
  {
    name: "Rodolfo C. Eregia, Jr.",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "eregia-754x1024.jpg",
  },
  {
    name: "Donie S. Jardeleza, MSCS",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "jardleza-754x1024.jpg",
  },
  {
    name: "Antonio M. Montaño, Jr.",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "montano-754x1024.jpg",
  },
  {
    name: "Rose Leah Joy A. Ojacastro, MSCS",
    role: "BSIT & BSIS Program",
    group: "Academic",
    photo: "ojacastro-754x1024.jpg",
  },
  {
    name: "Ma. Sheila C. Sapul, Ph.D.",
    role: "BSCS Program",
    group: "Academic",
    photo: "sapul-754x1024.jpg",
  },
  {
    name: "Chrislyn C. Castaño",
    role: "Secretary",
    group: "Staff",
    photo: "castano-754x1024.jpg",
  },
  {
    name: "A.M.P. Latter P. Taasan",
    role: "Computer Laboratory Technician",
    group: "Staff",
    photo: "taasan-754x1024.jpg",
  },
  {
    name: "Chriselda Elaine Ador",
    role: "Guidance Counselor",
    group: "Staff",
    photo: "ador-754x1024.jpg",
  },
  {
    name: "Donna May Rivera",
    role: "Library Liaison Officer",
    group: "Staff",
    photo: "rivera-754x1024.png",
  },
];

const visiblePeople = computed(() =>
  activeFilter.value === "All people"
    ? people
    : people.filter((person) => person.group === activeFilter.value),
);

function initials(name) {
  return name
    .replace(/,.*$/, "")
    .split(/\s+/)
    .filter((part) => /^[A-Z]/.test(part))
    .slice(0, 2)
    .map((part) => part[0])
    .join("");
}
</script>

<template>
  <section id="faculty" class="faculty-section">
    <div class="faculty-inner">
      <div class="faculty-heading">
        <div>
          <p class="faculty-eyebrow">
            <span></span> The people behind the work
          </p>
          <h2>Meet our<br /><em>Teachers.</em></h2>
        </div>
        <p class="faculty-intro">
          Good ideas grow with good people. Meet the faculty and staff who make
          the CCS community a place to learn, belong, and do your best work.
        </p>
      </div>

      <div class="faculty-tools">
        <div
          class="faculty-filters"
          role="group"
          aria-label="Filter people by role"
        >
          <button
            v-for="filter in filters"
            :key="filter"
            type="button"
            :class="{ 'is-active': activeFilter === filter }"
            :aria-pressed="activeFilter === filter"
            @click="activeFilter = filter"
          >
            {{ filter }}
          </button>
        </div>
        <span class="faculty-count"
          >{{ visiblePeople.length.toString().padStart(2, "0") }} PEOPLE</span
        >
      </div>

      <TransitionGroup name="people" tag="div" class="people-grid">
        <article
          v-for="(person, index) in visiblePeople"
          :key="person.name"
          class="person-row"
        >
          <span class="person-index">{{
            (index + 1).toString().padStart(2, "0")
          }}</span>
          <span class="person-portrait" :class="`monogram-${index % 4}`">
            <span class="portrait-fallback" aria-hidden="true">{{
              initials(person.name)
            }}</span>
            <img
              :src="`${portraitBase}${person.photo}`"
              :alt="person.name"
              loading="lazy"
              @error="$event.currentTarget.remove()"
            />
          </span>
          <span class="person-details"
            ><strong>{{ person.name }}</strong
            ><small>{{ person.role }}</small></span
          >
          <span class="person-group">{{
            person.group === "Academic" ? "ACADEMIC" : "STAFF"
          }}</span>
        </article>
      </TransitionGroup>


    </div>
  </section>
</template>

<style scoped>
.faculty-section {
  padding: 112px 24px 88px;
  color: #171717;
  background: #ffffff;
}

.faculty-inner {
  width: min(1120px, 100%);
  margin: 0 auto;
}

.faculty-heading {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 35px;
}

.faculty-eyebrow {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 0 0 22px;
  color: #424242;
  font-family: "DM Mono", "Courier New", monospace;
  font-size: 10px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

.faculty-eyebrow span {
  width: 19px;
  height: 1px;
  background: currentColor;
}

.faculty-heading h2 {
  margin: 0;
  font-family: "Manrope", "Trebuchet MS", sans-serif;
  font-size: clamp(49px, 5.8vw, 74px);
  font-weight: 600;
  letter-spacing: -0.075em;
  line-height: 0.99;
}

.faculty-heading h2 em {
  color: #424242;
  font-weight: 500;
}

.faculty-intro {
  width: min(350px, 40%);
  margin: 0 0 5px;
  color: #686b65;
  font-size: 13px;
  line-height: 1.8;
}

.faculty-tools {
  margin-top: 48px;
  padding-bottom: 14px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgba(23, 26, 24, 0.2);
}

.faculty-filters {
  display: flex;
  gap: 6px;
}

.faculty-filters button {
  min-height: 35px;
  padding: 0 13px;
  border: 1px solid transparent;
  color: #686b65;
  background: transparent;
  font-size: 11px;
  cursor: pointer;
  transition:
    color 0.2s,
    background 0.2s,
    border-color 0.2s;
}

.faculty-filters button:hover {
  color: #171a18;
  border-color: rgba(23, 26, 24, 0.2);
}

.faculty-filters button.is-active {
  color: #fff;
  border-color: #252525;
  background: #252525;
}

.faculty-count,
.person-index,
.person-group,
.faculty-footnote > span {
  color: #686b65;
  font-family: "DM Mono", "Courier New", monospace;
  font-size: 8px;
  letter-spacing: 0.09em;
}

.people-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  column-gap: 36px;
}

.person-row {
  min-height: 99px;
  display: grid;
  grid-template-columns: 24px 44px minmax(0, 1fr) auto;
  align-items: center;
  gap: 12px;
  border-bottom: 1px solid rgba(23, 26, 24, 0.13);
}

.person-index {
  color: #97978e;
}

.person-portrait {
  position: relative;
  width: 54px;
  height: 70px;
  display: grid;
  place-items: center;
  overflow: hidden;
  color: #252525;
  background: #d8d8d8;
  font-family: "Manrope", "Trebuchet MS", sans-serif;
  font-size: 12px;
  font-weight: 700;
}

.person-portrait img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 25%;
}

.portrait-fallback {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
  font-family: "Manrope", "Trebuchet MS", sans-serif;
  font-size: 12px;
  font-weight: 700;
}

.monogram-1 {
  color: #333333;
  background: #e5e5e5;
}
.monogram-2 {
  color: #444444;
  background: #eeeeee;
}
.monogram-3 {
  color: #222222;
  background: #cecece;
}

.person-details {
  min-width: 0;
  display: grid;
  gap: 5px;
}

.person-details strong {
  overflow-wrap: anywhere;
  font-family: "Manrope", "Trebuchet MS", sans-serif;
  font-size: 12px;
  font-weight: 700;
  line-height: 1.3;
}

.person-details small {
  color: #686b65;
  font-size: 10px;
  line-height: 1.4;
}

.person-group {
  align-self: center;
  white-space: nowrap;
}

.people-enter-active,
.people-leave-active,
.people-move {
  transition:
    opacity 0.18s,
    transform 0.18s;
}
.people-enter-from,
.people-leave-to {
  opacity: 0;
  transform: translateY(7px);
}
.people-leave-active {
  position: absolute;
}

.faculty-footnote {
  margin-top: 22px;
  display: flex;
  justify-content: space-between;
  gap: 20px;
}

.faculty-footnote a {
  font-size: 11px;
  font-weight: 600;
}

.faculty-footnote a b {
  margin-left: 8px;
  color: #424242;
  font-size: 15px;
}

@media (max-width: 760px) {
  .faculty-section {
    padding: 80px 21px 67px;
  }
  .faculty-heading {
    align-items: flex-start;
    flex-direction: column;
    gap: 20px;
  }
  .faculty-heading h2 {
    font-size: 55px;
  }
  .faculty-intro {
    width: min(100%, 400px);
  }
  .faculty-tools {
    margin-top: 32px;
  }
  .people-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 420px) {
  .person-row {
    grid-template-columns: 18px 42px minmax(0, 1fr);
    gap: 9px;
  }
  .person-portrait {
    width: 42px;
    height: 58px;
  }
  .person-details strong {
    font-size: 11px;
  }
  .person-group {
    display: none;
  }
  .faculty-filters button {
    padding: 0 9px;
    font-size: 10px;
  }
  .faculty-count {
    font-size: 7px;
  }
}
</style>
