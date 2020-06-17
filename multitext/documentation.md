---
layout: text
author: Patrick Callahan
permalink: /documentation/
---

# Pindar Opera Viewer Documentation

- [General Notes](#notes)
- [CTS/URNs](#cts)
  - [POV CTS/URNs Schema](#povCTS)
- [User's Guide to the POV](#guide)
  - [Utilizing the Frontmatter](#frontmatter)
  - [Revised Scholia Numbers](#scholiaNumbers)
  - [Managing your Columns](#columns)
- [Using the Advanced Search](#advancedSearch)

### <a id="notes">General Notes</a>
For greater detail on the methodology, textual criticism, and code behind the Pindar Opera Viewer, see [Chapter 1 of the dissertation]({{ site.baseurl }}/chapter_1/). Another good place to start is the [Homer Multitext](https://www.homermultitext.org/) project of Casey Dué Hackney and Mary Ebbott which is the most obvious and largest influence on the Pindar Opera Viewer.  

At the same time, the audience and scope of the two projects should be kept in mind. The two most obvious practical differences you will see are 1) the lack of manuscript images and 2) a layout designed more for the student than the researcher. It is to be hoped that future research and cooperation from libraries will see more work on the manuscripts themselves (esp. images) that will improve this site. The Advanced Search features of the Pindar Opera Viewer (still in development) are working on adopting a build of the <a href="https://github.com/cite-architecture/cite-app" target="blank">CITE-App</a> or similar webAPI for navigating the Pindar Multitext w.

### <a id="cts">CTS/URNs</a>
The text repository and the text references in code are organized according to the principles laid out by Christopher Blackwell and Neel Smith for [**C**anonical **T**ext **S**ervices](http://cite-architecture.org/ctsurn/overview/).

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

#### <a id="frontmatter">Utilizing the Frontmatter</a>

#### <a id="scholiaNumbers">Revised Scholia Numbers</a>

#### <a id="columns">Managing your Columns</a>

### <a id="advancedSearch">Using the Advanced Search</a>
At present the advanced search is still in development as I work on some additional coding skills to build a smoother webAPI experience. At present, users can fork the [texts repository](https://github.com/PRoryCallahan/Texts/tree/master/Pindar)
