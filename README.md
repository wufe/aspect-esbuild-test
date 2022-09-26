Cmd: `bazel build //package-a:bundle`

Error:

```sh
INFO: Analyzed target //package-a:bundle (28 packages loaded, 194 targets configured).
INFO: Found 1 target...
ERROR: C:/users/wufe/projects/cubbit/cubbit-test/package-a/BUILD:6:8: Bundling Javascript package-a/src/index.ts [esbuild] failed: (Exit 1): launcher.bat failed: error executing command 
  cd /d C:/users/wufe/_bazel_wufe/ml6oxqia/execroot/__main__
  SET BAZEL_BINDIR=bazel-out/x64_windows-fastbuild/bin
    SET ESBUILD_BINARY_PATH=../../../external/esbuild_windows-64/package/esbuild.exe
  bazel-out\x64_windows-opt-exec-2B5CBBC6\bin\external\esbuild_windows-64\launcher.bat --esbuild_args=package-a/bundle.args.json
# Configuration: 21fbbb65b48a2559691808d9463123cd3cef9795161b17c2ee1c994b1030ded0
# Execution platform: @local_config_platform//:host
FATAL: aspect_rules_js[js_binary]: node wrapper '/c/Users/wufe/_bazel_wufe/ml6oxqia/execroot/__main__/bazel-out/x64_windows-opt-exec-2B5CBBC6/bin/external/esbuild_windows-64/launcher.bat.runfiles/__main__/../esbuild_windows-64/launcher_node_wrapper/node.bat' is not executable
Target //package-a:bundle failed to build                                                                                                                            
INFO: Elapsed time: 0.498s, Critical Path: 0.22s                                                                                                                     
INFO: 2 processes: 2 internal.                                                                                                                                       
FAILED: Build did NOT complete successfully
```