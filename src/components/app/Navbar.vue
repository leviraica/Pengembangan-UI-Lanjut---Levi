<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()

const menus = [
  { name: 'Home', path: '/' },
  { name: 'About', path: '/about' },
  {
    name: 'Browse',
    path: '/browse',
    children: [
      {
        name: 'Event List',
        path: '/browse/events',
        children: [{ name: 'Event Detail (Contoh)', path: '/browse/events/1' }],
      },
      { name: 'Category', path: '/browse/category' },
    ],
  },
  { name: 'Contact', path: '/contact' },
]

const isActive = (path) => (path === '/' ? route.path === '/' : route.path.startsWith(path))
</script>

<template>
  <nav class="navbar">
    <div class="navbar-container">
      <router-link to="/" class="logo">Kumpul<span>.</span></router-link>

      <ul class="nav-menu">
        <li class="nav-item" v-for="menu in menus" :key="menu.name">
          <router-link :to="menu.path" class="nav-link" :class="{ active: isActive(menu.path) }">
            {{ menu.name }}
            <span v-if="menu.children">▾</span>
          </router-link>

          <ul v-if="menu.children" class="dropdown-menu">
            <li v-for="child in menu.children" :key="child.name" class="dropdown-item">
              <router-link :to="child.path" class="dropdown-link">
                {{ child.name }}
                <span v-if="child.children">▸</span>
              </router-link>

              <ul v-if="child.children" class="submenu">
                <li v-for="sub in child.children" :key="sub.name">
                  <router-link :to="sub.path" class="dropdown-link">{{ sub.name }}</router-link>
                </li>
              </ul>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  z-index: 999;
  background: var(--card);
  border-bottom: 3px solid var(--ink);
}
.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  max-width: 1100px;
  margin: 0 auto;
  padding: 0.8rem 2rem;
}
.logo {
  font-size: 1.6rem;
  font-weight: 700;
  text-decoration: none;
  color: var(--ink);
}
.logo span {
  color: var(--pink);
}
.nav-menu {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  list-style: none;
  flex-wrap: wrap;
}
.nav-item {
  position: relative;
  padding: 0.4rem 0;
}
.nav-link {
  display: flex;
  align-items: center;
  gap: 0.3rem;
  padding: 0.4rem 1rem;
  border: 2px solid transparent;
  border-radius: 8px;
  text-decoration: none;
  color: var(--ink);
  font-weight: 500;
}
.nav-link:hover {
  border-color: var(--ink);
}
.nav-link.active {
  background: var(--yellow);
  border-color: var(--ink);
  box-shadow: 3px 3px 0 var(--ink);
  font-weight: 700;
}

/* Dropdown */
.dropdown-menu,
.submenu {
  display: none;
  position: absolute;
  list-style: none;
  min-width: 220px;
  background: var(--card);
  border: 2px solid var(--ink);
  border-radius: 8px;
  box-shadow: var(--shadow);
}
.dropdown-menu {
  top: 100%;
  left: 0;
}
.submenu {
  top: -2px;
  left: 100%;
  margin-left: 6px;
}
.nav-item:hover > .dropdown-menu,
.dropdown-item:hover > .submenu {
  display: block;
  animation: fadeIn 0.15s ease;
}
.dropdown-item {
  position: relative;
}
.dropdown-link {
  display: flex;
  justify-content: space-between;
  padding: 0.65rem 1rem;
  text-decoration: none;
  color: var(--ink);
  font-weight: 500;
}
.dropdown-link:hover {
  background: var(--blue);
}

@media (max-width: 768px) {
  .navbar-container {
    flex-direction: column;
    padding: 0.8rem 1rem;
  }
}
</style>