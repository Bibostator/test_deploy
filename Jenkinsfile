node{
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
  
    stage 'Integration Test'
        sh "docker-compose -f dockers.yml up --force-recreate --abort-on-container-exit"
        sh "docker-compose -f dockers.yml down -v"
}