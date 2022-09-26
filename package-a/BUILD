load("@aspect_rules_esbuild//esbuild:defs.bzl", "esbuild")
load("@npm_aspect//:defs.bzl", "npm_link_all_packages")

npm_link_all_packages(name = "node_modules")

esbuild(
    name = "bundle",
    srcs = [
        "src/index.ts",
        ":node_modules/@wufe/mapper"
    ],
    # config = "esbuild.config.mjs",
    data = [
        
    ],
    entry_point = "src/index.ts",
)