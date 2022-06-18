<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Best-README-Template</h3>

  <p align="center">
    An awesome README template to jumpstart your projects!
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template">View Demo</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Report Bug</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

_Covid-19_ sebagai epidemik menyebabkan kekhawatiran kepada masyarakat dunia, begitu juga masyarakat di Indonesia. Masyarakat memerlukan sebuah platform yang memudahkannya untuk mengakses informasi seputar _Covid-19_ dengan cepat dan informatif. Maka dibuatkan sebuah _dashboard_ visualisasi interaktif untuk menampilkan informasi _Covid-19_ seputar Kasus Positif, Kasus Kematian dan Kasus Sembuh berdasarkan Provinsi di Indonesia Tingkat Nasional. 

Data yang digunakan didapat dari [kaggle](https://www.kaggle.com/datasets/riqulaziz/case-vaccination-covid19-indonesia-dataset) berisi data _Covid-19_ di Indonesia. _Dashboard_ dibuat menggunakan aplikasi `Tableau Desktop`. _Dashboard_ dibuat interaktif berdasarkan 8 worksheet diantaranya Peta Kasus Positif, Total Kasus, Covid Perhari dan Kasus Pertahun. 

_Dashboard_ juga ditampilkan pada tableau public, sehingga masyarakat secara mudah bisa melihat _dashboard_ visualisasi hanya bermodalkan internet. _Dashboard_ dapat diakses secara publik melalui [tautan](s.stis.ac.id/dashboard_221910726) berikut.

<!-- <p align="right">(<a href="#top">back to top</a>)</p> -->
<br/>



### Built With

Pada bagian ini akan dijabarkan berbagai _tools_ yang digunakan dalam pembuatan _dashboard_ visualisasi interaktif _Covid-19_.

* [Tableau](https://www.tableau.com/)
* [Tableau Public](https://public.tableau.com/en-us/s/)
* [Kaggle](https://www.kaggle.com/)

<br/>


<!-- GETTING STARTED -->
## Pengumpulan Data

Data dikumpulkan melalui situs [kaggle.com](https://www.kaggle.com/datasets/riqulaziz/case-vaccination-covid19-indonesia-dataset) yang menyediakan banyak _dataset_. Data yang diambil adalah data Kasus _Covid-19_ di Indonesia. Data ini memiliki 11 variabel diantaranya sebagai berikut.

| Variabel | Tipe Data |
| --- | --- |
| `date` | _Date_ |
| `province` | _Categorical_ |
| `daily case` | _Integer_ |
| `daily death` | _Integer_ |
| `daily recovered` | _Integer_ |
| `active case` | _Integer_ |
| `cumulative case` | _Integer_ |
| `cumulative death` | _Integer_ |
| `cumulative recovered` | _Integer_ |
| `cumulative active case` | _Integer_ |

<br/>

## Pre-processing Data

Data yang dikumpulkan tidak sepenuhnya bisa menampilkan visualisasi yang diinginkan. Perlu dilakukan pra-pemrosesan data agar visualisasi data dapat dilakukan semestinya. Dalam membuat peta tematik, memerlukan sebuah variabel `longitude` dan `latitude` yang di-generate agar menampilkan peta dunia. 

Selanjutnya, variabel provinsi memiliki 34 kategori yang unik didalamnya. Salah satu kategorinya yaitu _Daerah Istimewa Yogyakarta_. Kategori ini tidak terdeteksi oleh `latitude` dan `longitude` yang di-generate dikarenakan penamaan kategori tidak sesuai dengan semestinya yaitu _DI Yogyakarta_. Maka dari itu, dengan software _tableau desktop_, kami gantikan kategori _Daerah Istimewa Yogyakarta_ menjadi _DI Yogyakarta_. Sehingga peta tematik bisa dibuat untuk seluruh provinsi di Indonesia.

<br/>

## Visualisasi Data

### Peta Kasus Positif

Visualisasi data ini menampilkan peta tematik berdasarkan jumlah kasus kumulatif positif Covid-19. Peta ini ditampilkan melalui variabel _latitude_ yang diletakkan di bagian _rows_ dan _longitude_ yang diletakkan di bagian _columns_.

Berikutnya, variabel 'province' diletakkan ke menu marks sebagai _tooltip_, sehingga jika provinsi di Indonesia di-_hover_ maka akan memberikan memberikan keterangan nama provinsi dan total kasus per provinsi.

Selanjutnya meletakkan variabel `Cumulative Case` ke menu _marks_ dengan ukuran jumlah kasus kumulatif sebagai _color_. Hal ini akan memberikan warna pada tiap provinsi berdasarkan total kasus positifnya.

<div>
  <img src="images/peta-tematik.png" alt="Peta Tematik">
</div>

<br/>

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Malven's Flexbox Cheatsheet](https://flexbox.malven.co/)
* [Malven's Grid Cheatsheet](https://grid.malven.co/)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [React Icons](https://react-icons.github.io/react-icons/search)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
