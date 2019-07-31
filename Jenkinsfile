node{
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
  
    stage 'Integration Test'
        sh 'docker-compose -f dockers.yml up --build -d'
		sh 'docker exec -i jenkins sh -c "ps aux|grep jenkins"'
        sh 'docker-compose -f dockers.yml down -v'
}