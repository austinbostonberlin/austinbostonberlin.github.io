---
layout: page
title: Recommendations
---

<style>
ul { list-style-type: none; }
#filters a { padding-right: 5px; }
</style>

<div id="filters">
    <a href="#" onclick="document.querySelectorAll('li').forEach(elt => elt.style='')">reset</a>
</div>

<div id="recs">
    <div class="city:sf area:sfbay">
        <h2>San Francisco</h2>
        <ul>
            <li class="food" data-location="QH9C+F7 Duboce Triangle, San Francisco, CA">Beit Rima</li>
            <li class="food" data-location="QH5H+FR Mission District, San Francisco, CA">Garden Creamery</li>
            <li class="food" data-location="QH7M+7V Mission District, San Francisco, CA">Stable Cafe</li>
            <li class="tea vibes" data-location="QHF9+QP Lower Haight, San Francisco, CA">The Center</li>
            <li class="food" data-location="QHM8+F7 Western Addition, San Francisco, CA">Jane the Bakery</li>
            <li class="food" data-location="PHQM+MH Bernal Heights, San Francisco, CA">United Dumplings</li>
            <li class="food" data-location="QGGP+XG Inner Richmond, San Francisco, CA">Cinderella Bakery</li>
            <li class="books" data-location="QGMP+74 Inner Richmond, San Francisco, CA">Green Apple Books</li>
            <li class="park" data-location="QHG8+G3 Alamo Square, San Francisco, CA">Alamo Square Park</li>
            <li class="park" data-location="QG98+HR Golden Gate Park, San Francisco, CA">Golden Gate Park</li>
            <li class="park" data-location="RG3M+JX Presidio of San Francisco, San Francisco, CA">Crissy Field</li>
            <li class="park" data-location="QH5F+W5 Mission Dolores, San Francisco, CA">Dolores Park</li>
            <li class="food" data-location="QH6G+H9 Mission Dolores, San Francisco, CA">Tartine Bakery</li>
            <li class="books" data-location="QH5H+8C Dolores Heights, San Francisco, CA">Dog Eared Books</li>
            <li class="books" data-location="PHXF+27 Noe Valley, San Francisco, CA">Omnivore Books on Food</li>
            <li class="activity"><a href="https://crosstowntrail.org/">Crosstown Trail</a></li>
        </ul>
    </div>
    <div class="city:boston">
        <h2>Boston</h2>
        <ul>
            <li class="food" data-location="9WC3+64 Cambridge, Massachusetts">Oleana</li>
            <li class="food" data-location="9W2P+H5 Boston, Massachusetts">Maria's Taqueria</li>
            <li class="food" data-location="8WV2+68 Boston, Massachusetts">Phinista</li>
            <li class="food" data-location="CV4R+4M Medford, Massachusetts">Oasis Brazilian Restaurant</li>
            <li class="drinks" data-location="8WW7+VQ Boston, Massachusetts">Bukowski Tavern</li>
            <li class="drinks" data-location="8WW6+MG Boston, Massachusetts">The Bebop</li>
            <li class="coffee" data-location="8WR8+QJ Boston, Massachusetts">Farmers Horse Coffee</li>
            <li class="food" data-location="9W8C+HP Cambridge, Massachusetts">The Helmand</li>
            <li class="activity"><a href="https://www.bostontrails.org/">Walking City Trail</a></li>
        </ul>
    </div>
    <div class="city:nyc">
        <h2>New York City</h2>
        <ul>
            <li class="coffee" data-location="P2H8+CJ New York">Lê Phin</li>
            <li class="drinks" data-location="PX4R+JV New York">Overstory</li>
        </ul>
    </div>
    <div class="city:palo-alto area:sfbay">
        <h2>Palo Alto</h2>
        <ul>
            <li class="drinks" data-location="CRVQ+Q8 Palo Alto, California">The Rose &amp; Crown</li>
            <li class="drinks" data-location="CQJX+R9 Menlo Park, California">Dutch Goose</li>
        </ul>
        Sadly closed: Antonio's Nut House.
    </div>
    <div class="city:san-mateo area:sfbay">
        <h2>San Mateo</h2>
        <ul>
            <li class="food" data-location="HM8G+7V San Mateo, California">Urban Momo</li>
        </ul>
    </div>
    <div class="city:half-moon-bay area:sfbay">
        <h2>Half Moon Bay</h2>
        <ul>
            <li class="food" data-location="FH7C+X8 Half Moon Bay, California">San Benito Deli</li>
        </ul>
    </div>
</div>

<noscript>
<div style="background-color: #f8f3d6; padding: 5px;">
NOTE: This page provides some filtering using JS. It's perfectly usable without.
</div>
</noscript>

<script>
const allTags = new Set();
for (const div of document.querySelectorAll("#recs div")) {
    for (const tag of div.classList) {
        allTags.add(tag);
    }
    for (const entry of div.querySelectorAll("li")) {
        for (const tag of entry.classList) {
            allTags.add(tag);
        }
        for (const tag of div.classList) {
            entry.classList.add(tag);
        }
        const plusCode = entry.getAttribute("data-location");
        if (plusCode) {
            const locationLink = document.createElement("a");
            locationLink.setAttribute("href", `https://plus.codes/${plusCode}`);
            locationLink.append(document.createTextNode("(location)"));
            entry.append(document.createTextNode("\u00A0"));
            entry.append(locationLink);
        }
    }
}
const filters = document.querySelector("#filters");
for (const tag of [...allTags].sort()) {
    const a = document.createElement("a");
    a.setAttribute("href", "#");
    a.append(document.createTextNode(tag));
    a.onclick = () => {
        document.querySelectorAll("#recs li").forEach(elt => {
            if (!elt.classList.contains(tag)) {
                elt.style = "display: none;";
            }
        });
    }
    filters.append(a);
}
</script>