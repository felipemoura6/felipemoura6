<h1 align="center"> Me chamo Felipe Moura Ribeiro! </h1>


Bem-vindo ao meu perfil do GitHub! 👋

Me chamo Felipe, iniciando na área de TI (front-end e back-end). Aqui você encontrará uma variedade de projetos, desde pequenos scripts até projetos mais complexos. Fique à vontade para explorar e contribuir!




## Agradecimentos

Agradeço por visitar meu perfil! Sinta-se à vontade para explorar meus projetos e entrar em contato. Espero que encontre algo interessante aqui.







<h2 align="left">Hi 👋! My name is Felipe Moura Ribeiro</h2>

###

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=felipemoura6&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=felipemoura6&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph"  />
</div>

###

<img align="right" height="150" src="https://user-images.githubusercontent.com/74038190/213866269-5d00981c-7c98-46d7-8a8e-16f462f15227.gif">

###

<div align="left">
  
## Languages and Technologies:
 
- C / HTML5 / CSS3 / JavaScript / TypeScript / Python / SQL
  
[![My Languages](https://skillicons.dev/icons?i=js,html,css,ts,python,c)](https://skillicons.dev)




# Frameworks and Libraries:

- React / Vite / TailwindCSS / Prisma / NextJS / NodeJS

[![My Frameworks](https://skillicons.dev/icons?i=react,vite,tailwind,prisma,nextjs,nodejs)](https://skillicons.dev)


  
## Tools:

- Git / GitHub / Postman / Mysql / Arduino / Matlab
  
[![My Tools](https://skillicons.dev/icons?i=git,github,postman,mysql,arduino,matlab)](https://skillicons.dev)


</div>

###

## Social Media


<div align="left">
  <a href="https://www.instagram.com/felipe.moura_6/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="instagram logo" />
  </a>
  <a href="mailto:felipemourarb6@gmail.com">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="gmail logo" />
  </a>
  <a href="https://www.linkedin.com/in/felipe-moura-ribeiro-571b84232/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="linkedin logo" />
  </a>
</div>


###

<br clear="both">



# GitHub Action for generating a contribution graph with a snake eating your contributions.

# ![snake gif](https://github.com/your-user-name/your-user-name/blob/output/github-contribution-grid-snake.gif)

name: Generate Snake

# Controls when the action will run.
on:
  schedule:
      # every 12 hours
    - cron: "0 */12 * * *"

  # This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:
  
  # Also run on every push on the master branch
  push:
    branches:
    - main

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      - name: Clone repo
        uses: actions/checkout@v3
    
      - name: Generate the snake files in './dist/'
        uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |     
            dist/github-contribution-grid-snake.gif
            dist/github-contribution-grid-snake.svg
        env:
           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: Show build status
        run: git status

      - name: Push new files to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
          commit_message: Update snake animations
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
