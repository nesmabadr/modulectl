# Get the currently used golang install path (in GOPATH/bin, unless GOBIN is set)
ifeq (,$(shell go env GOBIN))
GOBIN=$(shell go env GOPATH)/bin
else
GOBIN=$(shell go env GOBIN)
endif

# Setting SHELL to bash allows bash commands to be executed by recipes.
# This is a requirement for 'setup-envtest.sh' in the test target.
# Options are set to exit when a recipe line exits non-zero or a piped command fails.
SHELL = /usr/bin/env bash -o pipefail
.SHELLFLAGS = -ec

##@ E2E Tests

test-scaffold-cmd:
	go test -tags=e2e ./scaffold -ginkgo.v -ginkgo.focus "Test 'scaffold' command"

test-create-cmd:
	go test -tags=e2e ./create -ginkgo.v -ginkgo.focus "Test 'create' command" -ginkgo.skip "Test 'create' command with private registry"

test-create-cmd-with-private-registry:
	go test -tags=e2e ./create -ginkgo.v -ginkgo.focus "Test 'create' command with private registry"
