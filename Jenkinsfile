node{
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
       # sh "docker-compose build -t build:B${BUILD_NUMBER} -f dockers.yml ."
       # sh "docker-compose build -t build:test-B${BUILD_NUMBER} -f dockers.yml ."
  
    stage 'Integration Test'
        sh "docker-compose -f dockers.yml up --force-recreate --abort-on-container-exit"
        sh "docker-compose -f dockers.yml down -v"
}