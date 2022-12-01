pipeline{
    agent {label 'ec2_slavenode'}
    stages {
    

     
        stage('Setup Python Virtual ENV'){
       
      steps  {
            sh '''
            chmod +x /home/ec2-user/workspace/Django-pipeline/django/scripts/envsetup.sh 
          bash  /home/ec2-user/workspace/Django-pipeline/django/scripts/envsetup.sh 
            '''}
        }
        
        stage('Run Make migration'){
       
      steps  {
            sh 'python /home/ec2-user/workspace/Django-pipeline/django/manage.py makemigrations pharma'
            
            }
        }
       
         stage('Run Collectstatic'){
       
      steps  {
            sh 'python /home/ec2-user/workspace/Django-pipeline/django/manage.py collectstaticv -y'
            
            }
        }
        
         stage('Run python migration'){
       
      steps  {
            sh 'python /home/ec2-user/workspace/Django-pipeline/django/manage.py migrate'
            
            }
        }
        
        
        stage('Run python manage command'){
       
      steps  {
            sh 'python /home/ec2-user/workspace/Django-pipeline/django/manage.py runserver 0.0.0.0:8000'
            
            }
        }
     
        
    }
}
