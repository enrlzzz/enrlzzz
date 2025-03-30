## Olá, eu sou o Enrico!

![Enrico's GitHub stats](https://github-readme-stats.vercel.app/api?username=enrlzzz&show_icons=true&theme=merko)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=enrlzzz&layout=compact)

name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: Enrico
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  
