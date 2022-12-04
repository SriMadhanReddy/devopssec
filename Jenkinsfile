pipeline{
    agent {label 'ec2_slavenode'}
    stages {
    

     
        stage('Setup Python Virtual ENV'){
       
      steps  {
            sh '''
            chmod +x /home/ec2-user/workspace/Devops_pipeline/scripts/envsetup.sh 
          bash  /home/ec2-user/workspace/Devops_pipeline/scripts/envsetup.sh 
            '''}
        }

         stage('Run python migration'){
       
      steps  {
            sh 'python3 /home/ec2-user/workspace/Devops_pipeline/manage.py migrate'
            
            }
        }
        
         stage('Run static code analysis'){
       
      steps  {
                /home/ec2-user/sonar-scanner/bin/sonar-scanner \
                -Dsonar.projectKey=sonarqube_jenkins \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://3.250.87.186:9000 \
                -Dsonar.login=efb89efcad2a95526d0a6275a184920d1789bb36
            }
        }
        
        
        stage('Run python manage command'){
       
      steps  {
            sh 'python3 /home/ec2-user/workspace/Devops_pipeline/manage.py runserver 0.0.0.0:8000'
            
            }
        }
     
        
    }
}
