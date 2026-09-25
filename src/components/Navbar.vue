<template>
  <header class="navbar">
    <div class="brand-logo">BUNGA ABADI — Onlineshop</div>
    <nav class="nav-links">
      <RouterLink to="/" class="nav-item">Landing</RouterLink>
      <RouterLink to="/product" class="nav-item">Product</RouterLink>
      <RouterLink to="/about" class="nav-item">About</RouterLink>
      <RouterLink to="/contact" class="nav-item">Contact</RouterLink>
    </nav>
  </header>
</template>
<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
  margin-bottom: 20px;
  font-family: 'Inter', system-ui, -apple-system, sans-serif;
}
.nav-links {
  display: flex;
  gap: 20px;

}
.nav-item {
  text-decoration: none;
  color: white;
  font-weight: 500;
  font-size: 0.9rem;
  transition: color 0.2s ease;
}

.nav-item:hover {
  color: white;
}
</style>