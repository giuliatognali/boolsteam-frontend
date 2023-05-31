<script>
export default {
  name: 'HeaderApp'
}
</script>

<template>
  <!-- header -->
  <header>
    <!-- header container -->
    <div id="header-container" class="ms-container d-flex justify-content-between">
      <div id="header-left" class="d-flex align-items-center justify-content-between">
        <!-- logo -->
        <div id="logo" class="d-flex align-items-center me-5 me-2-sm">
          <a href="#" id="logo">
            <img src="/logo_steam.svg" alt="logo">
          </a>
        </div>
        <!-- /logo -->
        <!-- nav -->
        <div id="nav" class="d-flex align-items-stretch">
          <ul class="d-flex align-items-stretch">
            <li>
              <a href="#" class="px-3">
                <h6>NEGOZIO</h6>
              </a>
            </li>
            <li>
              <a href="#" class="px-3">
                <h6>COMUNITÀ</h6>
              </a>
            </li>
            <li>
              <a href="#" class="px-3">
                <h6>INFORMAZIONI</h6>
              </a>
            </li>
            <li>
              <a href="#" class="px-3">
                <h6>ASSISTENZA</h6>
              </a>
            </li>
          </ul>
        </div>
        <!-- /nav -->
      </div>
      <!-- tools -->
      <div id="tools" class="align-self-start justify-self-end d-flex">
        <!-- download -->
        <div id="download" class="d-flex align-content-center">
          <a href="#" class="px-3 py-1">
            <i class="fa-solid fa-download me-2"></i>
            Installa Steam
          </a>
        </div>
        <!-- /download -->
        <div id="login-lang" class="d-flex">
          <!-- login -->
          <div id="login" class="my-1">
            <a href="http://127.0.0.1:8000/login" class="px-3">Accedi</a>
          </div>
          <!-- /login -->
          <!-- lang select -->
          <div id="lang">
            <div class="btn-group">
              <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-bs-toggle="dropdown"
                aria-expanded="false">
                Lingua
              </button>
              <ul class="dropdown-menu">
                <li>Italiano</li>
                <li>English</li>
              </ul>
            </div>
          </div>
          <!-- /lang select -->
        </div>
      </div>
      <!-- /tools -->
    </div>
    <!-- /header container -->
  </header>
  <!-- /header -->
</template>

<style lang="scss" scoped>
@use '../assets/scss/_partial/_variables' as *;

a {
  text-decoration: none;
  color: #a2a6a9;
}

header {
  background-color: #171a21;
  height: 7.8125rem;

  #header-container {
    margin: auto;
    height: 100%;

    #header-left {
      #logo {

        img {
          width: 11.25rem;
          max-height: 100%;
          max-height: 100%;
        }
      }

      #nav {
        height: 100%;

        ul {
          list-style: none;
          height: 100%;
          padding: 0;

          li {
            display: flex;
            align-items: stretch;

            a {
              line-height: 7.8125rem;
              display: flex;
              align-items: center;
            }

            a:hover {
              background-color: #242833;
            }
          }
        }
      }
    }

    #tools {
      a {
        color: #fbfaff;
      }

      #download {
        background-color: #587d13;
      }

      #login {
        a {
          border-right: 1px solid #fbfaff;
        }
      }

      #lang {
        background-color: inherit;
        border: none;
        color: #fbfaff;

        button {
          background-color: inherit;
          border: none;
          font-size: inherit;
        }

        li:hover {
          cursor: pointer;
        } 
      }
    }
  }
}
</style>
