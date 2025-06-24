(function ($) {
  "use strict";

  //======================================
  //Preloader.
  //======================================
  function preloader() {
    $("#ctn-preloader").fadeOut();
    $("#preloader").fadeOut();
  }

  $(window).on("load", function () {
    preloader();
    wowAnimation();
  });

  //======================================
  //Back To top.
  //======================================
  let back2top = $(".sigma-bt-top");

  back2top.on("click", function (e) {
    e.preventDefault();
    $("html, body").animate({ scrollTop: 0 }, 1500);
  });

  //======================================
  //Menu sticky & Scroll to top.
  //======================================

  $(window).on("scroll", function () {
    var scroll = $(window).scrollTop();
    if (scroll < 350) {
      $(".sigma-bt-top").removeClass("open");
    } else {
      $(".sigma-bt-top").addClass("open");
    }
  });

  $(window).on("scroll", function () {
    var scroll = $(window).scrollTop();
    if (scroll < 650) {
      $(".sigma-sticky-header").removeClass("sigma-sticky-active");
    } else {
      $(".sigma-sticky-header").addClass("sigma-sticky-active");
    }
  });

  //======================================
  //Menu.
  //======================================
  var menuItems = document.querySelectorAll(".main-menu li a");
  var currentPage = window.location.pathname.split("/").pop();

  menuItems.forEach(function (item) {
    var link = item.getAttribute("href").split("/").pop();

    if (link === currentPage) {
      item.parentElement.classList.add("current-menu-item");
    }
  });

  //======================================
  //Search Active.
  //======================================
  $(".sigma-header-search > a").on("click", function () {
    $(".sigma-header-top-search").slideToggle(400);
    return false;
  });

  //======================================
  //SubMenu Dropdown Toggle.
  //======================================
  if ($(".sigma-menu li.menu-item-has-children ul").length) {
    $(".sigma-menu li.menu-item-has-children").append('<div class="dropdown-btn"><span class="plus-line"></span></div>');
  }

  //======================================
  //Mobile Nav Hide Show
  //======================================
  const menuItemWithChild = $(".sigma-menu li.menu-item-has-children > a");

  if (menuItemWithChild.length) {
    menuItemWithChild.each(function () {
      $(this).append('<i class="fa-solid fa-arrow-down"></i>');
    });
  }

  if ($(".sigma-mobile-menu").length) {
    var mobileMenuContent = $(".sigma-menu-container .sigma-main-menu-wrap").html();
    var categoryMenuContent = $(".sigma-header-category").html();

    if (mobileMenuContent) {
      $(".sigma-mobile-menu .sigma-mobile-menu-box .sigma-mobile-menu-outer").append(mobileMenuContent);
    }

    if (categoryMenuContent) {
      $(".sigma-mobile-menu .sigma-mobile-menu-box .sigma-mobile-category-outer").append(categoryMenuContent);
    }

    //Dropdown Button
    $(".sigma-mobile-menu li.menu-item-has-children .dropdown-btn").on("click", function (e) {
      e.preventDefault();
      $(this).toggleClass("open");
      $(this).prev("ul").slideToggle(300);
    });

    //Menu Toggle Btn
    $(".sigma-mobile-menu-toggle").on("click", function () {
      $("body").addClass("sigma-mobile-menu-visible");
    });

    //Menu Toggle Btn
    $(".sigma-mobile-menu-backdrop, .sigma-mobile-menu .sigma-close-btn").on("click", function () {
      $("body").removeClass("sigma-mobile-menu-visible");
    });
  }

  //======================================
  //Category Menu Active
  //======================================
  $(".sigma-mobile-category-outer .sigma-category-menu").on("click", function () {
    $(".sigma-mobile-category-outer .sigma-category-items").slideToggle(300);
    return false;
  });

  //======================================
  // Hero Slider
  //======================================
  var swiper = new Swiper(".heroSlider", {
    slidesPerView: 1,
    spaceBetween: 30,
    loop: true,
    speed: 1500,
    autoplay: {
      delay: 5000,
      disableOnInteraction: false,
    },
    breakpoints: {
      768: {
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
      },
    },
  });

  //======================================
  // Testimonial Slider
  //======================================
  var swiper = new Swiper(".testimonialSlider", {
    slidesPerView: 1,
    spaceBetween: 30,
    loop: true,
    speed: 1500,
    autoplay: {
      delay: 5000,
      disableOnInteraction: false,
    },
    navigation: {
      nextEl: ".swiper-button-next",
      prevEl: ".swiper-button-prev",
    },
    breakpoints: {
      768: {
        slidesPerView: 2,
      },
      1100: {
        slidesPerView: 3,
      },
      1440: {
        slidesPerView: 4,
      },
    },
  });

  //======================================
  //Magnifification Popup.
  //======================================
  $(".sigma-play-btn").magnificPopup({
    disableOn: 300,
    type: "iframe",
    mainClass: "mfp-fade",
    removalDelay: 160,
    preloader: false,
    fixedContentPos: false,
  });

  //======================================
  //Counter up Active.
  //======================================
  new PureCounter({
    selector: ".purecounter",
    // decimals: 1,
  });

  //======================================
  // Testimonial Slider
  //======================================
  var swiper = new Swiper(".categoryMenu", {
    slidesPerView: 1,
    slidesPerGroup: 7,
    spaceBetween: 10,
    loop: false,
    speed: 1000,
    navigation: {
      nextEl: ".swiper-cat-menu-button-next",
      prevEl: ".swiper-cat-menu-button-prev",
    },
    breakpoints: {
      320: {
        slidesPerView: 1,
      },
      576: {
        slidesPerView: 1,
      },
      1200: {
        slidesPerView: 7,
      },
    },
  });

  //======================================
  //Random color category.
  //======================================
  /**
   * Selects one of the 11 colors of categories randomly for a single cat item
   * @returns {string} - A class name
   */
  const catList = $(".sigma-category-list > a");

  if (catList.length) {
    catList.each(function () {
      var randNum = Math.floor(Math.random() * 10) + 1;
      var className = "cat-theme-" + randNum;
      $(this).addClass(className);
    });
  }

  //======================================
  // Faq Section.
  //======================================

  function initializeAccordion() {
    const accordionHeaders = $(".sigma-accordion-title-wrap"); // Find all accordion headers on the page

    accordionHeaders.each(function () {
      const header = $(this);
      const accordionItem = header.closest(".sigma-accordion-item"); // Find the closest parent with class 'accordion-item'

      header.off("click").on("click", function () {
        const content = header.next();

        // Collapse all other accordion items on the page
        accordionHeaders.not(header).each(function () {
          const otherContent = $(this).next();
          const otherItem = $(this).closest(".sigma-accordion-item");
          otherContent.css("maxHeight", 0);
          otherItem.removeClass("item-active"); // Remove 'active' from other accordion items
        });

        // Toggle the clicked accordion item
        if (accordionItem.hasClass("item-active")) {
          accordionItem.removeClass("item-active");
          content.css("maxHeight", 0);
        } else {
          accordionItem.addClass("item-active");
          content.css("maxHeight", content[0].scrollHeight + "px");
        }
      });
    });
  }

  // Call the function to initialize the accordion
  initializeAccordion();

  //text copy.
  $(document).on("click", ".sigma-copy-btn", function () {
    let textToCopy = $(this).attr("text-to-copy");
    let tempElement = document.createElement("input");
    tempElement.value = textToCopy;
    document.body.appendChild(tempElement);
    tempElement.select();

    try {
      document.execCommand("copy");

      let tooltip = $(this).find(".sigma-tooltip");
      tooltip.text("URL Copied!");
      tooltip.addClass("success");

      setTimeout(function () {
        tooltip.removeClass("success");
        tooltip.text("Click to copy url");
      }, 2000);
    } catch (err) {
      console.error("Unable to copy text: " + err);
    }

    // Remove the temporary element
    document.body.removeChild(tempElement);
  });

  //text copy mobile.
  if ($(".sigmas-mobile-social-share-icon").length) {
    var mobileMenuContent = $(".sigma-social-share-wrap").html();
    $(".sigma-mss-router").append(mobileMenuContent);

    // Menu Toggle Btn
    $(".sigma-mss-option").on("click", function () {
      $(this).toggleClass("sigma-mss-visible");
      $(".sigma-ms-wrap").slideToggle(300);
    });
  }

  //======================================
  // Tutor Filter Option.
  //======================================
  document.addEventListener("DOMContentLoaded", function () {
    const selectLabel = document.querySelector(".sigma-form-select-label");
    const dropdown = document.querySelector(".sigma-form-select-dropdown");
    const options = document.querySelectorAll(".sigma-form-select-option span");

    if (selectLabel && dropdown) {
      // Toggle dropdown visibility
      selectLabel.addEventListener("click", function () {
        dropdown.style.display = dropdown.style.display === "block" ? "none" : "block";
      });

      // Close dropdown when clicking outside
      document.addEventListener("click", function (event) {
        if (!event.target.closest(".sigma-course-filter")) {
          dropdown.style.display = "none";
        }
      });

      // Update label with selected option and close dropdown
      options.forEach((option) => {
        option.addEventListener("click", function () {
          selectLabel.textContent = option.textContent;
          dropdown.style.display = "none";
          // Set the hidden select input value based on the selected option's data-key attribute
          document.querySelector("select[name='course_order']").value = option.getAttribute("data-key");
        });
      });
    }
  });

  //Filter.
  if ($(".sigma-mobile-cat-wrap").length) {
    var mobileFilter = $(".sigma-course-widget-filter-form").html();
    $(".sigma-mobile-cat-wrap .sigma-course-filter-outer").append(mobileFilter);

    //Menu Toggle Btn
    $(".sigma-course-filter-wrap .sigma-course-filter-icon").on("click", function () {
      $("body").toggleClass("sigma-course-filter-visible");
    });

    $(".sigma-mobile-filter-wrap .sigma-cfc-icon, .sigma-mobile-cat-wrap .sigma-mobile-filter-overlay").on("click", function () {
      $("body").removeClass("sigma-course-filter-visible");
    });
  }

  document.addEventListener("DOMContentLoaded", () => {
    // Tab functionality
    const tabs = document.querySelectorAll(".sigma-tab-item");
    const tabContents = document.querySelectorAll(".sigma-tab-content");

    tabs.forEach((tab) => {
      tab.addEventListener("click", () => {
        const target = tab.dataset.tab;

        tabs.forEach((t) => t.classList.remove("active"));

        tabContents.forEach((content) => content.classList.remove("active"));

        tab.classList.add("active");
        document.querySelector(target).classList.add("active");
      });
    });

    const showMoreBtn = document.querySelector(".sigma-show-more");
    const expandContent = document.querySelector(".sigma-cd-content-text");

    if (showMoreBtn && expandContent) {
      showMoreBtn.addEventListener("click", () => {
        expandContent.classList.toggle("sigma-content-collapsed");
        showMoreBtn.innerHTML = expandContent.classList.contains("sigma-content-collapsed") ? 'Show More <i class="fa-solid fa-angle-down mt-[3px]"></i>' : 'Show Less <i class="fa-solid fa-angle-up mt-[5px]"></i>';
      });
    }
  });

  document.addEventListener("DOMContentLoaded", function () {
    const accordionItems = document.querySelectorAll(".sigma-cd-accordion-item");

    accordionItems.forEach((item) => {
      const title = item.querySelector(".sigma-cda-title");
      const content = item.querySelector(".sigma-cda-content");

      // Initial state: Hide content
      content.style.maxHeight = "0px";

      title.addEventListener("click", function () {
        const isOpen = item.classList.contains("active");

        // Close all other items if you want only one open at a time
        accordionItems.forEach((otherItem) => {
          if (otherItem !== item) {
            otherItem.classList.remove("active");
            otherItem.querySelector(".sigma-cda-content").style.maxHeight = "0px";
          }
        });

        // Toggle the current item's state
        if (isOpen) {
          item.classList.remove("active");
          content.style.maxHeight = "0px";
        } else {
          item.classList.add("active");
          content.style.maxHeight = `${content.scrollHeight}px`;
        }
      });
    });
  });

  //Nice select.
  $(function () {
    if ($(".sigma-select").length > 0) {
      $(".sigma-select").niceSelect();
    }
  });
  

  // Add woo class
  // $(".sigma-animation").addClass("wow  animate__animated animate__fadeInUp");

  // $(document).on("ready", function () {
  //   let delay = 0.3;
  
  //   $(".sigma-animation-delay").each(function () {
  //     $(this)
  //       .attr("data-wow-delay", delay.toFixed(1) + "s");
  //     delay += 0.2;
  //   });
  // });
  

  //======================================
  // Testimonial Slider
  //======================================
  var swiper = new Swiper(".logoSlider", {
    slidesPerView: 1,
    slidesPerGroup: 1,
    spaceBetween: 10,
    speed: 1000,
    loop: true,
    speed: 1500,
    autoplay: {
      delay: 5000,
      disableOnInteraction: false,
    },
    breakpoints: {
      320: {
        slidesPerView: 2,
      },
      460: {
        slidesPerView: 3,
      },
      650: {
        slidesPerView: 4,
      },
      800: {
        slidesPerView: 5,
      },
      992: {
        slidesPerView: 6,
      },
    },
  });

  //======================================
  // Proiduct Gallary.
  //======================================
  var swiper = new Swiper(".sigma-product-gallary-thumb", {
    spaceBetween: 10,
    slidesPerView: 3,
    freeMode: true,
    watchSlidesProgress: true,
    direction: "horizontal",
    breakpoints: {
      576: {
        direction: 'vertical',
      },
    },
  });

  var swiper2 = new Swiper(".sigma-product-gallary", {
    spaceBetween: 10,
    loop: true,
    thumbs: {
      swiper: swiper,
    },
  });

  //======================================
  // Wow Active.
  //======================================
  function wowAnimation() {
    var wow = new WOW({
      boxClass: "wow",
      animateClass: "animate__animated",
      offset: 0,
      mobile: false,
      live: true,
    });
    wow.init();
  }
})(jQuery);

//======================================
// Course Filter.
//======================================
filterSelection("development"); //how many items are you show first time

function filterSelection(c) {
  var x, i;
  x = document.getElementsByClassName("sigama-course-filter"); // Number of items to show initially

  if (c == "all") c = "";
  for (i = 0; i < x.length; i++) {
    filterRemove(x[i], "show"); //show class remove
    if (x[i].className.indexOf(c) > -1) filteAdd(x[i], "show"); //This show class shows items
  }
}

function filteAdd(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    if (arr1.indexOf(arr2[i]) == -1) {
      element.className += " " + arr2[i];
    }
  }
}

function filterRemove(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    while (arr1.indexOf(arr2[i]) > -1) {
      arr1.splice(arr1.indexOf(arr2[i]), 1);
    }
  }
  element.className = arr1.join(" ");
}

 var $btnContainer = $(".sigma-cat-menu-itmes").first();
 if ($btnContainer.length) {
     var $btns = $btnContainer.find("button");
     $btns.on("click", function () {
         $(".sigma-cat-menu-active").removeClass("sigma-cat-menu-active");
         $(this).addClass("sigma-cat-menu-active");
     });
 }
