# Release Notes

## 0.114.0

### New Features

<!-- releasenotes/notes/release-0fde4f9-adding-liveness-readiness-probe-kanister-operator.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Added liveness and readiness probe for Kanister operator.

<!-- releasenotes/notes/release-1c2fda5-adding-patch-operation-kubeops-function.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Support patch operation in the KubeOps function.

<!-- releasenotes/notes/release-f398e80-adding-security-context-pod-container-kanister-operator.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Security Context of the Kanister operator pod can be configured using the helm fields `podSecurityContext` and `containerSecurityContext`.

### Bug Fixes

<!-- releasenotes/notes/release-01e6c0f-restore-log-stream.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Restored log stream functionality to improve debugging and monitoring capabilities.

<!-- releasenotes/notes/release-1b7dce3-fix-copy-container-override-multicontainerrun.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Make container override copied to background and output overrides for MultiContainerRun function.

<!-- releasenotes/notes/release-618246c-adding-failure-reasons-actionset-cr.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Added failure reasons in ActionSet CR.

<!-- releasenotes/notes/release-77ffaf0-updated-s3-profile-validation-documentation.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Improved S3 profile validation error messages.

### Deprecations

<!-- releasenotes/notes/deprecate-volume-snapshot-9fdf5b18604bd734.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Volume snapshot function such as CreateVolumeSnapshot, WaitForSnapshotCompletion, CreateVolumeFromSnapshot and DeleteVolumeSnapshot in favour of CSI snapshot functions.

### Other Notes

<!-- releasenotes/notes/deprecate-boringcrypto-3bf65cde59c99ce6.yaml @ b'cb7c6704e8a26b988e8f5eaa6681948989ab989d' -->
* Build process changed from using GODEBUG=boringcrypto to Go1.24 native crypto libraries for FIPS-compliant use.

## 0.113.0

### New Features

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Added gRPC call to support sending of UNIX signals to `kando` managed processes

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Added command line option to follow stdout/stderr of `kando` managed processes

<!-- releasenotes/notes/rds-credentials-1fa9817a21a2d80a.yaml @ b'c4534cdbb7167c6f854c4d7915dd22483f9486f9' -->
* Enable RDS functions to accept AWS credentials using a Secret or ServiceAccount.

### Bug Fixes

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* The Kopia snapshot command output parser now skips the ignored and fatal error counts

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Set default namespace and serviceaccount for MultiContainerRun pods

### Upgrade Notes

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Upgrade to K8s 1.31 API

### Deprecations

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* K8s VolumeSnapshot is now GA, remove support for beta and alpha APIs

### Other Notes

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Change `TIMEOUT_WORKER_POD_READY` environment variable to `KANISTER_POD_READY_WAIT_TIMEOUT`

<!-- releasenotes/notes/pre-release-0.113.0-591b9333c935aae6.yaml @ b'63c73f551aea7696a6dcaa77b628c24a9a53ea2b' -->
* Errors are now handled with [https://github.com/kanisterio/errkit](https://github.com/kanisterio/errkit) across the board

## 0.112.0

### New Features

<!-- releasenotes/notes/multi-container-run-function-d488516c0f3b22c6.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Introduced new Kanister function `MultiContainerRun` to run pods with two containers connected by shared volume.

<!-- releasenotes/notes/pre-release-0.112.0-78fed87c3f58d801.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Introduced a GRPC client/server to `kando` to run/check processes.

### Security Issues

<!-- releasenotes/notes/limit-rbac-kanister-operator-3c933af021b8d48a.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Enhanced security by removing the default `edit` `ClusterRoleBinding` assignment, minimizing the risk of excessive permissions.

### Upgrade Notes

<!-- releasenotes/notes/limit-rbac-kanister-operator-3c933af021b8d48a.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Users upgrading from previous versions should note that the `edit` `ClusterRoleBinding` is no longer included by default. They must now create their own `Role` / `RoleBinding` with appropriate permissions for Kanister's Service Account in the application's namespace.

### Other Notes

<!-- releasenotes/notes/pre-release-0.112.0-78fed87c3f58d801.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Update ubi-minimal base image to ubi-minimal:9.4-1227.1726694542.

<!-- releasenotes/notes/pre-release-0.112.0-78fed87c3f58d801.yaml @ b'a72741deb67462a80a93856794d8a5c4425bb7c1' -->
* Add `gci` and `unparam` linters to test packages.

## 0.111.0

### New Features

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Add support for Read-Only and Write Access Modes when connecting to the Kopia Repository Server in `kando`.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Add support for Cache Size Limits to the `kopia server start` command.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Add support to pass labels and annotations to the methods that create/clone VolumeSnapshot and VolumeSnapshotContent resources.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Support `image` argument for `ExportRDSSnapshotToLocation` and `RestoreRDSSnapshot` functions to override default postgres-kanister-tools image.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Added support to customise the labels and annotations of the temporary pods that are created by some Kanister functions.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Added two new fields, `podLabels` and `podAnnotations`, to the ActionSet. These fields can be used to configure the labels and annotations of the Kanister function pod run by an ActionSet.

### Security Issues

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Update Go to 1.22.7 to pull in latest security updates.

### Other Notes

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Update ubi-minimal base image to ubi-minimal:9.4-1227.1725849298.

<!-- releasenotes/notes/pre-release-0.111.0-478149ddf5d56f80.yaml @ b'd207c416a800fdff15f570275f1e3dfe0ede4ffe' -->
* Add `stylecheck`, `errcheck`, and `misspel` linters to test packages.

## 0.110.0

### New Features

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Split parallelism helm value into dataStore.parallelism.upload and dataStore.parallelism.download to be used separately in BackupDataUsingKopiaServer and RestoreDataUsingKopiaServer

### Bug Fixes

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Make pod writer exec wait for cat command to finish. Fixes race condition between cat cat command end exec termination.

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Make sure all storage providers return similar error if snapshot doesn't exist, which is expected by DeleteVolumeSnapshot

### Other Notes

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Update ubi-minimal base image to ubi-minimal:9.4-1194

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Update errkit to v0.0.2

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Switch pkg/app to errkit

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Switch pkg/kopia to errkit

<!-- releasenotes/notes/pre-release-0.110.0-a47623540224894a.yaml @ b'fffef729e348ce0cf8bba3646303460d5e37fe16' -->
* Switch pkg/kube to errkit
