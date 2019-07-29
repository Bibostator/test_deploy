node('docker-agent') {
 
    stage 'Checkout'
        checkout scm
    stage 'Build & UnitTest'
        sh "docker build -t Build:B${BUILD_NUMBER} -f Dockerfile ."
        sh "docker build -t Build:test-B${BUILD_NUMBER} -f Dockerfile.Integration ."
  
    stage 'Integration Test'
        sh "docker-compose -f dockers.yml up --force-recreate --abort-on-container-exit"
        sh "docker-compose -f dockers.yml down -v"
}