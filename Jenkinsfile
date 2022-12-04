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

         stage('Make migrations'){
       
      steps  {
            sh 'python3 /home/ec2-user/workspace/Devops_pipeline/manage.py migrate'
            
            }
        }
        
         stage('Run Static code Analysis'){
       
      steps  {
            sh '''
            chmod +x /home/ec2-user/workspace/Devops_pipeline/scripts/codeanalysisis.sh
            bash  /home/ec2-user/workspace/Devops_pipeline/scripts/codeanalysisis.sh
            '''}
            }
        
        stage('Deploy application'){
       
      steps  {
            sh 'python3 /home/ec2-user/workspace/Devops_pipeline/manage.py runserver 0.0.0.0:8000'
            
            }
        }
     
        
    }
}
