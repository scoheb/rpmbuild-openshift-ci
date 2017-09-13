node() {

  openshift.verbose(true)

  openshift.withCluster() {
    echo "Hello from default project: ${openshift.project()}"
    result = openshift.startBuild("rpmbuild", "--commit", "refs/pull/281/head", "--wait")

    // The name of the operation performed (i.e. "delete")
    echo "Overall status: ${result.operation}"

    // The number of sub-actions run
    echo "Overall status: ${result.status}"

    // First OpenShift command which was executed
    echo "Actions performed: ${result.actions[0].cmd}"

    // Additional command reference information
    echo "Reference information: ${result.actions[0].reference}"

    // Aggregate output from all sub-actions
    def out = result.out.trim()
    echo "Operation output: " + out

    def imageStr = openshift.describe(out)
    // The name of the operation performed (i.e. "delete")
    echo "Overall status: ${imageStr.operation}"

    // The number of sub-actions run
    echo "Overall status: ${imageStr.status}"

    // First OpenShift command which was executed
    echo "Actions performed: ${imageStr.actions[0].cmd}"

    // Additional command reference information
    echo "Reference information: ${imageStr.actions[0].reference}"

    // Aggregate output from all sub-actions
    def out2 = imageStr.out.trim()
    echo "Operation output: " + out2

  }
}
