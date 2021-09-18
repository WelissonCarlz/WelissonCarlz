## Oiii! Eu sou o Welisson Carlos
✔️ Atualmente estudante do Instituto Federal de  Goiás - Campus Anápolis 

<div>
  <a href="https://github.com/welissoncarlz">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=welissoncarlz&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
</div>
  
<div style="display: inline_block"><br>
  <img align="center" alt="We-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="We-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="We-CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
  <img align="center" alt="We-Python" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg">
  <img align="right" alt="We-yoda" height="200" width="300"  src="https://data.whicdn.com/images/152926369/original.gif">
</div>
  
 
  
nome : gerar animação

em :
  # executado automaticamente a cada 6 horas
  horário :
    - cron : " 0 * / 6 * * * " 
  
  # permite executar manualmente o trabalho a qualquer momento
  workflow_dispatch :
  
  # executar em cada push no branch master
  empurre :
    ramos :
    - mestre
    
  

empregos :
  gerar :
    roda em : ubuntu-mais recente
    tempo limite-minutos : 10

    passos :
      # gera um jogo de cobra a partir de um gráfico de contribuições do usuário github (<github_user_name>), produza uma animação SVG em <svg_out_path>
      - nome : gerar github-contribition-grid-snake.svg
        usa : Platane / snk @ master
        com :
          github_user_name : $ {{github.repository_owner}}
          svg_out_path : dist / github-Contribution-grid-snake.svg

      # empurre o conteúdo de <build_dir> para um branch
      # o conteúdo estará disponível em https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/ <file>, ou como página do github
      - name : envia github-customization-grid-snake.svg para o branch de saída
        usa : crazy-max/ghaction-github-pages@v2.5.0
        com :
          target_branch : output
          build_dir : dist
        env :
          GITHUB_TOKEN : $ {{secrets.GITHUB_TOKEN}}
