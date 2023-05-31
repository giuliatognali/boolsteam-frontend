<script>
export default {
  name: 'FooterApp'
}
</script>

<template>
  <!-- footer -->
  <footer class="p-3">
    <div id="footer-container" class="ms-big-container">
      <!-- footer top -->
      <div id="footer-top" class="pt-2">
        <!-- logos -->
        <div id="logos" class="d-flex justify-content-between mb-1">
          <a href="#" id="logo">
            <img src="/valve.png" alt="logo">
          </a>
          <a href="#" id="logo">
            <img src="/logo_steam.svg" alt="logo">
          </a>
        </div>
        <!-- /logos -->
        <div class="px-3">
          <p class="my-0">2023 Valve Corporation Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat,
              ut voluptatum eum deleniti voluptate molestias reiciendis nisi ipsa sit corrupti, beatae architecto
              et.</p>
          <div class="d-flex">
            <p>IVA inclusa nel prezzo (ove applicabile).</p>
            <!-- nav -->
            <nav>
              <ul class="d-flex">
                <li><a href="#" class="px-2 nav-border">Informativa sulla privacy</a></li>
                <li><a href="#" class="px-2 nav-border">Informazioni legali</a></li>
                <li><a href="#" class="px-2 nav-border">Contratto di sottoscrizione a Steam</a></li>
                <li><a href="#" class="px-2 nav-border">Rimborsi</a></li>
                <li><a href="#" class="px-2">Cookie</a></li>
              </ul>
            </nav>
            <!-- /nav -->
          </div>
        </div>
      </div>
      <!-- /footer top -->
      <!-- footer bottom -->
      <div id="footer-bottom">
        <!-- nav -->
        <nav class="mt-3">
          <ul class="d-flex p-0">
            <li><a href="#" class="ps-3 pe-2 nav-border">Informazioni su valve</a></li>
            <li><a href="#" class="px-2 nav-border">Impieghi</a></li>
            <li><a href="#" class="px-2 nav-border">Steamworks</a></li>
            <li><a href="#" class="px-2 nav-border">Distribuzione su steam</a></li>
            <li><a href="#" class="px-2 nav-border">Assistenza</a></li>
            <li><a href="#" class="px-2 nav-border">Buoni regalo</a></li>
            <li>
              <a href="#" class="px-2 nav-border" id="fb-link">
                <img src="/facebook-logo.png" alt="logo fb">
                Steam
              </a>
            </li>
            <li>
              <a href="#" class="px-2" id="tw-link">
                <img src="/twitter.png" alt="logo fb">
                @steam
              </a>
            </li>
          </ul>
        </nav>
        <!-- /nav -->
      </div>
      <!-- /footer bottom -->
    </div>
  </footer>
  <!-- /footer -->
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

.nav-border {
  border-right: 2px solid #35383f;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
  color: #ced5db;
  font-weight: 600;
}

nav {
  li {
    a {
      
    }
  }
}

footer {
  background-color: $ms-dark-primary;
  color: $ms-text;
  font-size: .875rem;

  #footer-container {
    margin: auto;

    #footer-top {
      border-top: 2px solid #35383f;
      border-bottom: 2px solid #35383f;

      #logos {
        img {
          width: 8.75rem;
        }
      }
    }

    #footer-bottom {
      #fb-link,
      #tw-link {
        img {
          width: 1.25rem;
          vertical-align: middle;
        }
      }
    }
  }

}
</style>
