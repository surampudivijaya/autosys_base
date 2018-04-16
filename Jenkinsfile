node ("master"){

  stage('clean working directory'){
     deleteDir()
  }
  
  stage('SCM Checkout'){
    checkout SCM
  }
 
 stage('scan for repolist and trigger build for repos'){
   def repoList = []
   def myrepos = readJSON file: './repos.json'
   def repos_list = myrepos.repos
   repos_list.each {
      echo "triggers a build for scan of repo, ${it.url}\n"
       echo "https://jenkins.nml.com/job/autosys/job/auto-autosys1/buildWithParameters?token=autosys&repo_url=${it.url}"
   }
 }

}
