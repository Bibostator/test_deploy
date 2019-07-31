node{
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
  
    stage 'Integration Test'
        sh "docker-compose -f dockers.yml up --build --abort-on-container-exit"
		sh 'docker exec -ti jenkins sh -c "cd app/ && bundle exec rspec -f documentation"'
        sh "docker-compose -f dockers.yml down -v"
}