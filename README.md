<div>
<h1 align="center"> 𝐇𝐞𝐥𝐥𝐨 𝐭𝐡𝐞𝐫𝐞, 𝐟𝐞𝐥𝐥𝐨𝐰! - Psalm 1. <img src="https://github.com/ABSphreak/ABSphreak/blob/master/gifs/Hi.gif?raw=true" width="30px"></h2>
	
</div>


<p align="center">
<img width="520px" src="https://user-images.githubusercontent.com/74038190/235224431-e8c8c12e-6826-47f1-89fb-2ddad83b3abf.gif">
 </p>

<p align="center">
	<a href="https://www.linkedin.com/in/jrfertonani/"> <img width="180px" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linkedin/linkedin-original-wordmark.svg" /></a>
</p>

<p align="center">
	<img width="70px" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original-wordmark.svg" />
	<img width="80px" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/spring/spring-original-wordmark.svg"  />
 	<img width="80px" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg" />
	<img width="60px" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/angular/angular-original.svg" />
	<img width="55px" src="https://icongr.am/devicon/typescript-original.svg?size=60&color=currentColor" />
</p>

<p align="center">
  <a href="https://github.com/jrfertonani">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=jrfertonani&show_icons=true&theme=dark"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=jrfertonani&layout=compact&langs_count=7&theme=dark"/>
</p>

<p align="center">  💬 Ask me about 💚JAVA -💚 MYSQL - About teamwork and fun.</p>



name: Generate Snake

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: ${{ secrets.jrfertonani }}
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: main
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


