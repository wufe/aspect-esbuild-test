load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "aspect_rules_js",
    sha256 = "0707a425093704fab05fb91c3a4b62cf22dca18ea334d8a72f156d4c18e8db90",
    strip_prefix = "rules_js-1.3.1",
    url = "https://github.com/aspect-build/rules_js/archive/refs/tags/v1.3.1.tar.gz",
)

load("@aspect_rules_js//js:repositories.bzl", "rules_js_dependencies")

rules_js_dependencies()

load("@rules_nodejs//nodejs:repositories.bzl", "DEFAULT_NODE_VERSION", "nodejs_register_toolchains")

nodejs_register_toolchains(
    name = "nodejs",
    node_version = DEFAULT_NODE_VERSION,
)

load("@aspect_rules_js//npm:npm_import.bzl", "npm_translate_lock")

npm_translate_lock(
    name = "npm_aspect",
    pnpm_lock = "//:pnpm-lock.yaml"
)

load("@npm_aspect//:repositories.bzl", "npm_repositories")

npm_repositories()

http_archive(
    name = "aspect_rules_esbuild",
    sha256 = "1e365451341ffb2490193292dfd9953f2ca009586c2381cb4dc08d01e48866b7",
    strip_prefix = "rules_esbuild-0.12.0",
    url = "https://github.com/aspect-build/rules_esbuild/archive/refs/tags/v0.12.0.tar.gz",
)

######################
# rules_esbuild setup #
######################

# Fetches the rules_esbuild dependencies.
# If you want to have a different version of some dependency,
# you should fetch it *before* calling this.
# Alternatively, you can skip calling this function, so long as you've
# already fetched all the dependencies.
load("@aspect_rules_esbuild//esbuild:dependencies.bzl", "rules_esbuild_dependencies")

rules_esbuild_dependencies()

# If you didn't already register a toolchain providing nodejs, do that:
load("@rules_nodejs//nodejs:repositories.bzl", "DEFAULT_NODE_VERSION", "nodejs_register_toolchains")

nodejs_register_toolchains(
    name = "node",
    node_version = DEFAULT_NODE_VERSION,
)

# Register a toolchain containing esbuild npm package and native bindings
load("@aspect_rules_esbuild//esbuild:repositories.bzl", "LATEST_VERSION", "esbuild_register_toolchains")

esbuild_register_toolchains(
    name = "esbuild",
    esbuild_version = LATEST_VERSION,
)