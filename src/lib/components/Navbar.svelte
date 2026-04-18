<script lang='ts'>
  import { ChevronDown, Globe, MailOpen, Menu, Moon, Sun, ChevronLeft } from '@lucide/svelte'
  import { page } from '$app/stores'
  import Logo from './Logo.svelte'

  const invitationLinks = [
    { href: '/invitations/wedding', label: 'Düğün-Nikah Davetiyesi' },
    { href: '/invitations/birthday', label: 'Doğum Günü' },
    { href: '/invitations/babyshower', label: 'Bebek Partisi' },
    { href: '/invitations/circumcision', label: 'Sünnet Merasimi' },
    { href: '/invitations/trip', label: 'Gezi & Grup Etkinlikleri' },
    { href: '/invitations/opening', label: 'Açılış Davetiyeleri' },
    { href: '/invitations/business', label: 'İş-Fuar Davetiyeleri' },
    { href: '/invitations/concert', label: 'Konser Davetiyesi' },
    { href: '/invitations/special', label: 'Özel Davetler' },
  ]

  let isOpen = $state(false)
  let timeoutId: any
  let dropdownRef: HTMLElement

  function handleEnter() {
    if (timeoutId)
      clearTimeout(timeoutId)
    isOpen = true
  }

  function handleLeave() {
    timeoutId = setTimeout(() => {
      isOpen = false
    }, 1500)
  }

  function closeMenu() {
    isOpen = false
    if (timeoutId)
      clearTimeout(timeoutId)
  }

  function handleOutsideClick(e: MouseEvent) {
    if (isOpen && dropdownRef && !dropdownRef.contains(e.target as Node)) {
      closeMenu()
    }
  }
</script>

<svelte:window onclick={handleOutsideClick} />

<nav class='navbar bg-base-200 sticky top-0 z-50 px-4 md:px-8'>
  <div class='navbar-start'>
    <!-- Mobil Hamburger -->
    <label for='mobile-drawer' class='btn btn-ghost btn-circle lg:hidden' aria-label='Menüyü aç'>
      <Menu class='w-6 h-6' />
    </label>

    <!-- Premium Geri Butonu -->
    {#if $page.url.pathname !== '/'}
      <div class="mr-2 ml-1">
        <a href='/' 
           class='group relative flex items-center justify-center w-10 h-10 rounded-xl bg-base-100 shadow-[0_4px_12px_rgba(0,0,0,0.05)] border border-base-content/5 hover:shadow-primary/20 hover:border-primary/30 transition-all duration-300 active:scale-95' 
           title='Anasayfaya Dön'>
           
          <!-- Şık Pırıltı Arka Planı -->
          <div class="absolute inset-0 rounded-xl bg-gradient-to-br from-primary/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>

          <!-- Pürüzsüz Yuvarlanmış Üçgen (SVG) -->
          <svg class="relative z-10 w-4 h-4 text-base-content/50 group-hover:text-primary transform group-hover:-translate-x-0.5 transition-all duration-300" 
               viewBox="0 0 24 24" fill="currentColor" stroke="currentColor" stroke-width="1.5" stroke-linejoin="round">
            <path d="M17.5 4.3c0-1.54-1.7-2.47-2.98-1.65L4.44 10.1c-1.19.76-1.19 2.53 0 3.29l10.08 6.45c1.28.82 2.98-.11 2.98-1.65V4.3Z" />
          </svg>
        </a>
      </div>
    {/if}

    <!-- Logo -->
    <a href='/' class='outline-none'>
      <Logo />
    </a>
  </div>

  <div class='navbar-center hidden lg:flex'>
    <ul class='menu menu-horizontal px-1 gap-1'>
      <!-- Davetiyeler Dropdown (JS Hover with Delay) -->
      <li class="dropdown dropdown-bottom {isOpen ? 'dropdown-open' : ''}"
          bind:this={dropdownRef}
          onmouseenter={handleEnter}
          onmouseleave={handleLeave}>
        <div tabindex='0' role='button' class='btn btn-ghost btn-sm gap-1 normal-case font-medium hover:bg-base-300'>
          Davetiyeler
          <ChevronDown class='w-4 h-4 opacity-70' />
        </div>
        <ul class='dropdown-content menu z-100 p-2 shadow-xl bg-base-100 rounded-box w-64 border border-base-200'>
          {#each invitationLinks as link}
            <li><a href={link.href} class='active:bg-primary/10' onclick={closeMenu}>{link.label}</a></li>
          {/each}
          <div class='divider my-1'></div>
          <li><a href='/invitations/custom' class='bg-primary/10 text-primary font-bold hover:bg-primary/20' onclick={closeMenu}>Özelleştir (Kendin Tasarla)</a></li>
        </ul>
      </li>
      <li><a href='/pricing'>Ücretler</a></li>
      <li><a href='/contact'>İletişim</a></li>
    </ul>
  </div>

  <div class='navbar-end gap-1'>
    <!-- Dil Seçeneği -->
    <div class='dropdown dropdown-end'>
      <div tabindex='0' role='button' class='btn btn-ghost btn-sm btn-circle' aria-label='Dil Seç'>
        <Globe class='w-5 h-5' />
      </div>
      <ul class='dropdown-content menu z-100 p-2 shadow-xl bg-base-100 rounded-box w-40 border border-base-200'>
        <li><button class='active:bg-primary/10 flex items-center gap-2'><span class="text-lg leading-none">🇹🇷</span> Türkçe</button></li>
        <li><button class='active:bg-primary/10 flex items-center gap-2'><span class="text-lg leading-none">🇬🇧</span> İngilizce</button></li>
        <li><button class='active:bg-primary/10 flex items-center gap-2'><span class="text-lg leading-none">🇷🇺</span> Rusça</button></li>
      </ul>
    </div>

    <!-- Tema Değiştirici -->
    <label class='swap swap-rotate btn btn-ghost btn-sm btn-circle'>
      <input type='checkbox' class='theme-controller' value='dark' />
      <Sun class='swap-on w-5 h-5' />
      <Moon class='swap-off w-5 h-5' />
    </label>

    <!-- Satın Al Butonu -->
    <a href='/order' class='btn btn-primary btn-sm md:btn-md shadow-lg shadow-primary/25 hover:shadow-primary/40 transition-all ml-1'>
      Satın Al
    </a>
  </div>
</nav>
