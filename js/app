/**
 * 
 * Manipulating the DOM exercise.
 * Exercise programmatically builds navigation,
 * scrolls to anchors from navigation,
 * and highlights section in viewport upon scrolling.
 * 
 * Dependencies: None
 * 
 * JS Version: ES2015/ES6
 * 
 * JS Standard: ESlint
 * 
 */

/**
 * Define Global Variables
 * 
 */ //
//select all sections in a variable
const sections = document.querySelectorAll('section');
const ul = document.querySelector('#navbar__list');
//create a fragment
const fragment = document.createDocumentFragment();
/**
 * End Global Variables
 * Start Helper Functions
 * 
 */


//create li elment and links for each sections and put name for it 
sections.forEach((section) => {
    //create new li element foe each section
    let newli = document.createElement('li');
    //create new links for each section
    let newlink = document.createElement('a');
    //get the name of the section
    let sectitle = section.getAttribute('data-nav');
    //create textnode 
    let textnode = document.createTextNode(sectitle);
    //set the links style
    newlink.className = "menu__link";
    //append link with text node 
    newlink.appendChild(textnode);
    //append li with link
    newli.appendChild(newlink);
    //append fragment with li
    fragment.appendChild(newli);
    //add scroll event listener for smooth scroll
    newlink.addEventListener("click", function(scroll) {
        section.scrollIntoView({ behavior: "smooth" });
    })
});
//ul with fragment
ul.appendChild(fragment);


// Add class 'active' to section when near top of viewport
window.addEventListener("scroll", function(scroll) {

    sections.forEach((section) => {
        let activesec = section.getBoundingClientRect();
        let activesectiontitle = section.getAttribute("data-nav");
        //remove all active class from sections
        section.classList.remove("active");
        //check if the section in viewport 
        if (activesec.top > -300 && activesec.bottom < 300) {
            //set the section as an active section
            section.classList.add("active");

            const navitems = document.querySelectorAll("ul li");

            navitems.forEach((navItem) => {
                const navtitle = navItem.textContent;
                navItem.classList.remove("active");
                if (activesectiontitle == navtitle) {

                    navItem.classList.add("active");
                }
            });

            console.log("I'm in the viewPort");
        } else {
            console.log("I'm not in the view port");
        }
        console.log(activesec.top);


    });
});

// Scroll to section on link click
function myFunction(active_section) {
    const links = document.querySelectorAll('a');
    let data_value = active_section.getAttribute('data-nav');
    // Set section as active
    links.forEach((link) => {
        if (link.textContent == data_value) {
            link.classList.remove('active-link');

            link.classList.add('active-link');
        }
    });
}
// Scroll to anchor ID using scrollTO event


/**
 * End Main Functions
 * Begin Events
 * 
 */

// Build menu
