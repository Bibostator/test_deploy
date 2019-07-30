node{
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
  
    stage 'Integration Test'
        sh "docker-compose -f dockers.yml up"
        sh "docker-compose -f dockers.yml down -v"
}