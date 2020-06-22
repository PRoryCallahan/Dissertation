---
layout: default
author: Patrick Callahan
permalink: /documentation/
---

<h1 class="display-2 text-center">Pindar Opera Viewer Documentation</h1>
<hr>
- [General Notes](#notes)
- [A Student's Guide to Scholia](#introScholia)
  - [What are Scholia?](#scholiaDef)
  - [Understanding Scholia Reference #s](#understandScholia)
  - [Scholiastic Greek Tips](#scholiaCheatsheet)
- [CTS/URNs](#cts)
  - [POV CTS/URNs Schema](#povCTS)
- [User's Guide to the POV](#guide)
  - [Utilizing the Frontmatter](#frontmatter)
  - [Managing your Columns](#columns)
  - [Reading a Scholion in the POV](#scholiaNumbers)
  - [App Crit Tools in the POV](#appCrit)
- [Using the Advanced Search](#advancedSearch)
<hr>
### <a id="notes">General Notes</a>
For greater detail on the methodology, textual criticism, and code behind the Pindar Opera Viewer, see [Chapter 1 of the dissertation]({{ site.baseurl }}/chapter_1/). Another good place to start is the [Homer Multitext](https://www.homermultitext.org/) project of Casey Dué Hackney and Mary Ebbott which is the most obvious and largest influence on the Pindar Opera Viewer.  

At the same time, the audience and scope of the two projects should be kept in mind. The two most obvious practical differences you will see are 1) the lack of manuscript images and 2) a layout designed more for the student than the researcher. It is to be hoped that future research and cooperation from libraries will see more work on the manuscripts themselves (esp. images) that will improve this site. The Advanced Search features of the Pindar Opera Viewer (still in development) are working on adopting a build of the <a href="https://github.com/cite-architecture/cite-app" target="blank">CITE-App</a> or similar webAPI for navigating the Pindar Multitext w.

### <a id="introScholia">A Student's Guide to Scholia</a>

Before discussing the technology and interface of the Pindar Opera Viewer, it might be best for student users and even some researchers in need of a refresher.

Two excellent books have emerged in recent years as guides to ancient scholia. First, for the very beginner there is Eleanor Dickey's [*Ancient Greek Scholarship*](https://www.amazon.com/Ancient-Greek-scholarship-Understanding-Commentaries/dp/0195312937). This will also point you to further reading on particular corpora of scholia to various authors. For those looking for a next step to understanding the scholarship behind scholia, there is René Nünlist's [*The Ancient Critic at Work*](https://www.amazon.com/Ancient-Critic-Work-Concepts-Criticism/dp/1107403049/ref=sr_1_1?dchild=1&keywords=rene+nunlist&qid=1592493835&s=books&sr=1-1).

For other recommended readings, please see the [Works Cited]({{ site.baseurl }}/works_cited).

Still, for those looking to dive right in. Here is a crash course on the Pindar scholia.

#### <a id="scholiaDef">What are Scholia?</a>

[Scholia](https://en.wikipedia.org/wiki/Scholia) [singular: scholium/scholion < <span lang="grc">σχόλιον</span> "comment, interpretation"] are the ancient commentaries and various other metadata that are preserved (often in the margins) of our manuscripts to Classical texts. In origin, many started out as individual *hypomnemata* [< (sing.) ὑπόμνημα "explanatory notes, commentary"] composed by scholars in Alexandria, Pergamum, and elsewhere. In the case of the Pindar scholia, these were combined in an epitome by Didymus with his own additional comments, and then they were further redacted and epitomated for various purposes in various editions from the period of the Second Sophistic to the Byzantine period. For more on the development of the Pindar scholia and a review of the various theories of how they moved from separate booklets into the margins of the odes themselves, see [Chapter 1]({{ site.baseurl }}/chapter_1/).

Today, the Pindar scholia, like many scholia continue to serve as the foundation of most commentaries. And yet, the needs of modern publishing also preclude their inclusion alongside the text on which they comment. Instead, they can be found in various printed editions with modern reference numbers and lemmata to help the reader refer them back to the text on which they comment.

#### <a id="understandScholia">Understanding Scholia Reference #s</a>

The first thing to note is that scholia reference numbers are usually tied to the reference schema adopted for the text on which they comment, except that the scholion is usually preceded by an "Σ" to signify that this is a scholion in reference to that portion of the core text. Until the Pindar Opera Viewer and the Pindar Multitext that lies behind it, previous editions of the scholia vetera used a number system based on the old colometry of Heyne (1798) rather than the modern colometry of Böckh (1811-1821). For example,

<table class="table table-bordered">
  <thead>
    <tr class="table-danger">
      <th scope="col">Pindar, Olympian 11.4-6</th>
      <th scope="col">Scholia Vetera</th>
      <th scope="col">Scholia Vetera Trans.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row"><span lang="grc">
      <ol class="mb-0 verse" start="4">
      <li>εἰ δὲ σὺν πόνῳ τις εὖ πράσσοι, μελιγάρυες ὕμνοι</li>
      <li>ὑστέρων ἀρχὰ λόγων</li>
      <li>τέλλεται καὶ πιστὸν ὅρκιον μεγάλαις ἀρεταῖς.</li>
      </ol>
      </span></th>
      <td><b>Σ O.11.5. τέλλεται:</b> ἀντὶ τοῦ τέλλονται οἱ ὕμνοι· ἑνικὸν ἀντὶ πληθυντικοῦ.</td>
      <td><b>Σ O.11.5. τέλλεται:</b> in place of "the hymns are accomplished". singular in place of plural.</td>
    </tr>
  </tbody>
</table>

The obvious positive for this is that scholia line numbers align with what would have been the line numbers of Pindar's odes at the time of the MSS in which they are found. The obvious negative is that it adds a layer of disconnect between the scholia vetera and the modern editions of Pindar used by both students and researchers. The POV numbers scholia first according to Böckh line number with Heyne line number in parentheses.

<table class="table table-bordered">
  <thead>
    <tr class="table-danger">
      <th scope="col">lemma</th>
      <th scope="col">Modern Ode Reference #</th>
      <th scope="col">Old Scholia Reference #</th>
      <th scope="col">POV Reference #</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">τέλλεται</th>
      <td>O.11.6</td>
      <td>Σ Ο.11.5.</td>
      <td>Σ O.11.6. (5.)</td>
    </tr>
  </tbody>
</table>

In the case of Σ O.11.6. (5.) and its comment on τέλλεται, there is not much consternation for those looking to reconcile the Heyne and Böckh numbers, but in a longer ode, esp. *Pythian* 4 the discrepancy between the two sets of numbers can become a significant annoyance.

#### <a id="scholiaCheatsheet">Scholiastic Greek Tips</a>

For those who have learned Greek in order to read literary authors, scholia present a few challenges that often dissuade the neophyte without a reference guide. First, because these are para-textual elements, copyists and editors have often given them less care than the texts on which they comment. (This makes them extraordinarily interesting because so-called "corruptions" in scholia are often a reflection of a more creative space that reveal the reading habits and much more about these often anonymous Late Antique and Medieval scribes and scholars). Second, scholia as epitomes often use a kind of shorthand and sentence structure particular to themselves. Third, scholia often speak in their own argot. They rely frequently on grammatical terminology that no Greek student would have learned when preparing to read Homer, Sappho, or Plato, e.g. πληθυντικός as used in Σ O.11.6. (5.) above. And they use familiar words with unfamiliar and hyper-specific meanings.

*In the future, this space will include an index to the most frequent and useful terms and habits of the Pindar scholia that would be of use to the average Greek student.*
<!--[Build out (searchable?) index of frequently used terms in scholia sim. to Dickey?]-->

### <a id="cts">CTS/URNs</a>
Earlier in this guide, we discussed human reference numbers for texts. But in crafting a digital edition of the Pindar multitext, we need a way of referencing portions of a text that is both human- and machine-readable. Therefore, the text repository and the text references in code are organized according to the principles laid out by Christopher Blackwell and Neel Smith for [**C**anonical **T**ext **S**ervices](http://cite-architecture.org/ctsurn/overview/).

Before the Pindar Opera Viewer, among existing CTS/URNs three(3) **Textgroups** existed for Pindar and the Pindar scholia in the **CTSNamespace** of 'greekLit':

<div id="accordion">
  <div class="card">
    <div class="card-header" id="pindarTLG">
      <h4 class="mb-0">
        <button class="btn btn-link collapsed" data-toggle="collapse" data-target="#pindarBookTLG" aria-expanded="false" aria-controls="pindarBookTLG">
          Pindar: urn:cts:greekLit:tlg0033
        </button>
      </h4>
    </div>

    <div id="pindarBookTLG" class="collapse" aria-labelledby="pindarBookTLG" data-parent="#accordion">
      <div class="card-body">
      <dl>
        <dt>Olympian:</dt>
        <dd> urn:cts:greekLit:tlg0033:tlg001</dd>
        <dt>Pythian:</dt>
        <dd> urn:cts:greekLit:tlg0033:tlg002</dd>
        <dt>Nemean:</dt>
        <dd> urn:cts:greekLit:tlg0033:tlg003</dd>
        <dt>Isthmian:</dt>
        <dd> urn:cts:greekLit:tlg0033:tlg004</dd>
      </dl>
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="pindarScholiaTLG">
      <h4 class="mb-0">
        <button class="btn btn-link collapsed" data-toggle="collapse" data-target="#pindarScholiaBookTLG" aria-expanded="false" aria-controls="pindarScholiaBookTLG">
          Pindar Scholia: urn:cts:greekLit:tlg5034
        </button>
      </h4>
    </div>
    <div id="pindarScholiaBookTLG" class="collapse" aria-labelledby="pindarScholiaBookTLG" data-parent="#accordion">
      <div class="card-body">
      <dl>
        <dt>Olympian scholia:</dt>
        <dd>urn:cts:greekLit:tlg5034:tlg001a</dd>
        <dt>Pythian scholia:</dt>
        <dd>urn:cts:greekLit:tlg5034:tlg001b</dd>
        <dt>Nemean scholia:</dt>
        <dd>urn:cts:greekLit:tlg5034:tlg001c</dd>
        <dt>Isthmian scholia:</dt>
        <dd>urn:cts:greekLit:tlg5034:tlg001d</dd>
      </dl>
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="pindarVitaeTLG">
      <h4 class="mb-0">
        <button class="btn btn-link collapsed" data-toggle="collapse" data-target="#pindarVitaeEtcTLG" aria-expanded="false" aria-controls="pindarVitaeEtcTLG">
          Vitae Pindari et varia de Pindaro: urn:cts:greekLit:tlg4170
        </button>
      </h4>
    </div>
    <div id="pindarVitaeEtcTLG" class="collapse" aria-labelledby="pindarVitaeEtcTLG" data-parent="#accordion">
      <div class="card-body">
      <dl>
        <dt>Vita Ambrosiana:</dt>
        <dd>urn:cts:greekLit:tlg4170.tlg001a</dd>
        <dt>Vita Thomana et hypothesis Olympiorum:</dt>
        <dd>urn:cts:greekLit:tlg4170.tlg001b</dd>
        <dt>Vita metrica:</dt>
        <dd>urn:cts:greekLit:tlg4170.tlg001c</dd>
        <dt>Pentathlon et de novem lyricis:</dt>
        <dd>urn:cts:greekLit:tlg4170.tlg001d</dd>
      </dl>
      </div>
    </div>
  </div>

</div>

<br>
To separate Pindar from the scholia vetera was understandable under the limitations imposed by physical publishing. For example, the Snell-Maehler Tuebner edition of Pindar is a slim volume of 162 pages. The scholia vetera edited by Drachmann stretch over three volumes of 395 pages (Olympians), 270 pages (Pythians), and 402 pages (Nemeans & Isthmians).
<br><br>
For reasons justified in the [dissertation]({{ site.baseurl }}/chapter_1/) itself, the Pindar Opera Viewer has returned the text of the scholia and vitae back into conversation with the text of the odes. To avoid confusion with the existing CTS/URNs, we follow a unique CTS/URN schema with not only a different Textgroup but also CTSNamespace.

#### <a id="povCTS">POV CTS/URNs Schema</a>

**Upper Level Citation**<br>
urn:cts:pov:pindar:pindar001

**Specific Lines/Word Citation**<br>
urn:cts:pov:pindar:pindar001:msA:callahan001:11.14@κελαδήσω

<table class="table">
  <thead>
    <tr>
      <th scope="col">POV</th>
      <th scope="col">Component</th>
      <th scope="col">Note</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">urn</th>
      <td>Namespace Identifier</td>
      <td>&lt;NID&gt;, required by the URN standard.</td>
    </tr>
    <tr>
      <th scope="row">:cts</th>
      <td>Namespace Specific String</td>
      <td>&lt;NSS&gt;, required by the URN standard, identifies this URN as a CTS URN.</td>
    </tr>
    <tr>
      <th scope="row">:pov</th>
      <td>CTS Namespace</td>
      <td>An abbreviation for an identifying authority for some domain of texts.</td>
    </tr>
    <tr>
      <th scope="row">:pindar</th>
      <td>TextGroup</td>
      <td>In this case, the textgroup known as “Pindar”, which includes his epinikia, the fragments from his other books of poetry, the frontmatter surrounding those books, and the scholia and other metadata around the odes. pindarMultitext is the identifier asserted by the Center for Hellenic Studies’ First Thousand Years of Greek project, abbreviated by the namespace `pov`</td>
    </tr>
    <tr>
      <th scope="row">:pindar001</th>
      <td>Work</td>
      <td>The identifier for the Olympian Odes, a notional work, encompassing every edition and translation of that work.</td>
    </tr>
    <tr>
      <th scope="row">:msA</th>
      <td>Version</td>
      <td>An identifier for an edition of the Olympian Odes, the version of the Greek text that appears on the Ambrosianus C 222 inf MS, as referenced by Anders Bjørn Drachmann, in this case.</td>
    </tr>
    <tr>
      <th scope="row">:callahan001</th>
      <td>Exemplar</td>
      <td>An identifier for a particular exemplar of Ambrosianus C 222 inf, here edited by myself.</td>
    </tr>
    <tr>
      <th scope="row">:11.14</th>
      <td>Citation</td>
      <td>The Olympian Odes are canonically cited by Ode Number + Poetic Line; this two-level citation hierarchy, then, consists of two values separated by a .: Ode 11, line 1.</td>
    </tr>
    <tr>
      <th scope="row">@κελαδήσω</th>
      <td>Subreference</td>
      <td>This identifies the string κελαδήσω in line 14 of Olympian 11 of my version of Ambrosianus C 222 inf of the Olympians Odes of Pindar.</td>
    </tr>
  </tbody>
</table>

### <a id="guide">User's Guide to the POV</a>

[insert video guide]

#### <a id="frontmatter">Utilizing the Frontmatter</a>

[insert video guide]

What you see:

[number overlay on screen sot of frontmatter]

1. Ode #
2. Scholia Title
3. Trans. of Scholia Title
4. Frontmatter title
5. Meter
  - Collapsible Illustration of Meter
6. Date of Victory
7. Victor
8. Hometown of Victor
9. Event
10. Scholia Inscriptions Toggle
  - Scholia Inscriptions

#### <a id="columns">Managing your Columns</a>

Below the frontmatter you encounter the POV column control panel. While future editions will include more than just the text of Pindar and the scholia vetera, what you have now are the ability to toggle on and off:

1. a Greek text of the ode.
2. a Greek text and/or English translation of a revised and updated version of the scholia vetera, still largely based on Anders Bjørn Drachmann's 1903-1927 editions.
3. Greek texts and English translations of the scholia from individual MSS.

With responsive columns built on Bootstrap's CSS grid system, **mobile users** should see columns shift vertically. **Laptop users:** we recommend you bring up only 3-6 columns at any given time if you want to see them parallel in an aesthetically pleasing manner. **Desktop users** hypothetically can access up to 12 parallel columns (depending on the size of your display) but we encourage a max of 6 parallel columns active at any one time. Please report any problems with column responsiveness to pcallahan [at] fordham.edu.

#### <a id="scholiaNumbers">Reading a Scholion in the POV</a>

For those unfamiliar with scholia...

#### <a id="appCrit">App Crit Tools in the POV</a>

<mark class="A"></mark>

### <a id="advancedSearch">Using the Advanced Search</a>
At present the advanced search is still in development as I work on some additional coding skills to build a smoother webAPI experience. At present, users can fork the [texts repository](https://github.com/PRoryCallahan/Texts/tree/master/Pindar)
