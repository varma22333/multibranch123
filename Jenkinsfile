properties([
  parameters([
    string(name: 'param1', description: 'Possible options: a b c d', defaultValue: ''),
    string(name: 'param2', description: 'Possible options: e f g h', defaultValue: ''),
    string(name: 'param3', description: 'Possible options: k l m n', defaultValue: ''),
    string(name: 'param4', description: 'Possible options: 1 2 3 4', defaultValue: ''),
    
    
  ])
])
node ("master") {
stage("checkout")
{
  echo "${param1}"
  echo "${param2}"
  echo "${param3}"
  echo "${param4}"
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/varma22333/multibranch123.git']]])
}

stage("Build")
{
  
  sh 'ls -ltr'
   sh 'chmod 777 test.sh' 
  sh './test.sh'
     
}
stage("QA")
{
    
}
stage("slack")
{
    slackSend color: 'Red', message: 'Sandeep - The great'
}

}
