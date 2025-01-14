# migrate

## Overview

Small program that simplifies migration between 2 Kyma versions. It compares manifests files created by Kyma CLI dry-run to identify orphaned resources after upgrading Kyma to higher versions. Can optionally create a shell script containing kubectl deletion commands to remove these resources.

## Usage

Supports three arguments to compare dry-run manifests of Kyma installations.
1. Path to the first manifests file of the the installed version
2. Path to the second manifests file of the upgrade version
3. Optional: Name for the deletion script to be generated. If used creates a script that deletes orphaned resources

Example:
```
go build -o migrate
./migrate -output testdata/created-cleanup.sh testdata/kyma-1.yaml  testdata/created-cleanup.sh
```
