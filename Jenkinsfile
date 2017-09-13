node() {
  openshift.withCluster() {
    echo "Hello from default project: ${openshift.project()}"
    build = openshift.startBuild("rpmbuild", "--commit", "refs/pull/281/head", "--wait", "--env", "mytag=tom")
  }
}
