node() {
  openshift.withCluster() {
    echo "Hello from default project: ${openshift.project()}"
    build = openshift.startBuild("rpmbuild2", "--commit", "refs/pull/281/head", "--wait", "--follow")
  }
}
