package(default_visibility = ["//visibility:public"])

filegroup(
    name = "srcs",
    srcs = glob(["**"]) + [
        "//third_party/ijar:srcs",
        "//third_party/iossim:srcs",
        "//third_party/java/buck-ios-support:srcs",
        "//third_party/java/dd_plist:srcs",
        "//third_party/java/j2objc:srcs",
        "//third_party/java/jarjar:srcs",
        "//third_party/java/jdk/langtools:srcs",
        "//third_party/py/concurrent:srcs",
        "//third_party/py/gflags:srcs",
        "//third_party/py/mock:srcs",
    ],
)

filegroup(
    name = "protoc",
    srcs = select({
        ":windows_mingw": ["protobuf/protoc-windows-x86_32.exe"],
        ":windows_msys64_mingw64": ["protobuf/protoc-windows-x86_64.exe"],
        ":windows_clang": ["protobuf/protoc-windows-x86_32.exe"],
        ":darwin": ["protobuf/protoc-osx-x86_32.exe"],
        ":k8": ["protobuf/protoc-linux-x86_64.exe"],
        ":piii": ["protobuf/protoc-linux-x86_32.exe"],
        ":arm": ["protobuf/protoc-linux-arm32.exe"],
        ":freebsd": ["protobuf/protoc-linux-x86_32.exe"],
    }),
)

filegroup(
    name = "d3-js",
    srcs = glob(["javascript/d3/**/*.js"]),
)

filegroup(
    name = "jquery",
    srcs = glob(["javascript/jquery/**/*.jslib"]),
)

java_import(
    name = "aether",
    jars = [
        "aether/aether-api-1.0.0.v20140518.jar",
        "aether/aether-spi-1.0.0.v20140518.jar",
        "aether/aether-transport-http-1.0.0.v20140518.jar",
        "aether/aether-connector-basic-1.0.0.v20140518.jar",
        "aether/aether-transport-classpath-1.0.0.v20140518.jar",
        "aether/aether-transport-wagon-1.0.0.v20140518.jar",
        "aether/aether-impl-1.0.0.v20140518.jar",
        "aether/aether-transport-file-1.0.0.v20140518.jar",
        "aether/aether-util-1.0.0.v20140518.jar",
    ],
)

java_import(
    name = "android_common",
    jars = [
        "android_common/com.android.tools.build_builder_0.13.3.jar",
        "android_common/com.android.tools.build_builder-model_0.13.3.jar",
        "android_common/com.android.tools.build_manifest-merger_23.1.3.jar",
        "android_common/com.android.tools_common_23.1.3.jar",
        "android_common/com.android.tools_sdk-common_23.1.3.jar",
        "android_common/com.android.tools_sdklib_23.1.3.jar",
        "android_common/com.android.tools.layoutlib_layoutlib_23.1.3.jar",
    ],
)

java_import(
    name = "apache_commons_codec",
    jars = ["apache_commons_codec/commons-codec-1.9.jar"],
)

java_import(
    name = "apache_commons_collections",
    jars = ["apache_commons_collections/commons-collections-3.2.1.jar"],
)

java_import(
    name = "apache_commons_compress",
    jars = ["apache_commons_compress/apache-commons-compress-1.9.jar"],
)

java_import(
    name = "apache_commons_logging",
    jars = ["apache_commons_logging/commons-logging-1.1.1.jar"],
)

java_import(
    name = "apache_commons_pool2",
    jars = ["apache_commons_pool2/commons-pool2-2.3.jar"],
)

java_import(
    name = "apache_httpclient",
    jars = ["apache_httpclient/httpclient-4.2.5.jar"],
)

java_import(
    name = "apache_httpcore",
    jars = ["apache_httpcore/httpcore-4.2.4.jar"],
)

java_import(
    name = "apache_velocity",
    jars = ["apache_velocity/velocity-1.7.jar"],
)

java_import(
    name = "asm",
    jars = ["asm/asm-5.0.4.jar"],
)

java_import(
    name = "asm-commons",
    jars = ["asm/asm-commons-5.0.4.jar"],
)

java_import(
    name = "asm-util",
    jars = ["asm/asm-util-5.0.4.jar"],
)

java_plugin(
    name = "auto_annotation_plugin",
    processor_class = "com.google.auto.value.processor.AutoAnnotationProcessor",
    deps = [
        ":apache_commons_collections",
        ":apache_velocity",
        ":asm",
        ":auto_common",
        ":auto_service",
        ":auto_value_value",
        ":guava",
        ":jsr305",
        ":tomcat_annotations_api",
    ],
)

java_import(
    name = "auto_common",
    jars = ["auto/auto-common-0.3.jar"],
)

java_import(
    name = "auto_service",
    jars = ["auto/auto-service-1.0-rc2.jar"],
)

java_plugin(
    name = "auto_service_plugin",
    processor_class = "com.google.auto.service.processor.AutoServiceProcessor",
    deps = [
        ":auto_common",
        ":auto_service",
        ":guava",
    ],
)

java_plugin(
    name = "auto_value_plugin",
    processor_class = "com.google.auto.value.processor.AutoValueProcessor",
    deps = [
        ":apache_commons_collections",
        ":apache_velocity",
        ":asm",
        ":auto_common",
        ":auto_service",
        ":auto_value_value",
        ":guava",
        ":jsr305",
        ":tomcat_annotations_api",
    ],
)

java_library(
    name = "auto_value",
    exported_plugins = [
        ":auto_annotation_plugin",
        ":auto_value_plugin",
    ],
    exports = [
        ":auto_value_value",
        ":tomcat_annotations_api",
    ],
)

java_import(
    name = "auto_value_value",
    jars = ["auto/auto-value-1.0.jar"],
)

java_import(
    name = "bytebuddy",
    jars = ["bytebuddy/byte-buddy-dep-0.7-rc6.jar"],
    deps = [
        ":asm",
        ":asm-commons",
        ":asm-util",
    ],
)

java_import(
    name = "gson",
    jars = ["gson/gson-2.2.4.jar"],
)

java_import(
    name = "error_prone",
    jars = [
        "error_prone/error_prone_core-2.0.6-20151001-884eec772c13541a7b1af249a68373cd9f30e488.jar",
        "error_prone/error_prone_annotations-2.0.6-20151001-884eec772c13541a7b1af249a68373cd9f30e488.jar",
    ],
    exports = [
        ":checker_framework_dataflow",
        ":jformatstring",
    ],
)

java_import(
    name = "jformatstring",
    jars = [
        "jformatstring/jFormatString-3.0.0.jar",
    ],
)

java_import(
    name = "checker_framework_dataflow",
    jars = [
        "checker_framework_dataflow/dataflow-1.8.10.jar",
    ],
)

# For bootstrapping JavaBuilder
filegroup(
    name = "error_prone-jars",
    srcs = [
        "checker_framework_dataflow/dataflow-1.8.10.jar",
        "error_prone/error_prone_annotations-2.0.6-20151001-884eec772c13541a7b1af249a68373cd9f30e488.jar",
        "error_prone/error_prone_core-2.0.6-20151001-884eec772c13541a7b1af249a68373cd9f30e488.jar",
        "jformatstring/jFormatString-3.0.0.jar",
    ],
)

java_import(
    name = "guava",
    jars = ["guava/guava-18.0.jar"],
)

# For bootstrapping JavaBuilder
filegroup(
    name = "guava-jars",
    srcs = ["guava/guava-18.0.jar"],
)

java_import(
    name = "jgit",
    jars = ["jgit/org.eclipse.jgit-4.0.1.201506240215-r.jar"],
)

java_import(
    name = "joda_time",
    jars = ["joda_time/joda-time-2.3.jar"],
)

java_import(
    name = "jsch",
    jars = ["jsch/jsch-0.1.51.jar"],
)

java_import(
    name = "jsr305",
    jars = ["jsr305/jsr-305.jar"],
)

# For bootstrapping JavaBuilder
filegroup(
    name = "jsr305-jars",
    srcs = ["jsr305/jsr-305.jar"],
)

java_import(
    name = "jsr330_inject",
    jars = ["jsr330_inject/javax.inject.jar"],
)

java_import(
    name = "maven",
    jars = glob(["maven/*.jar"]),
)

java_import(
    name = "maven_model",
    jars = [
        "maven_model/maven-aether-provider-3.2.3.jar",
        "maven_model/maven-model-3.2.3.jar",
        "maven_model/maven-model-builder-3.2.3.jar",
        "maven_model/maven-repository-metadata-3.2.3.jar",
    ],
)

java_import(
    name = "plexus_component_annotations",
    jars = ["plexus_component_annotations/plexus-component-annotations-1.6.jar"],
)

java_import(
    name = "plexus_interpolation",
    jars = ["plexus_interpolation/plexus-interpolation-1.22.jar"],
)

java_import(
    name = "plexus_utils",
    jars = ["plexus_utils/plexus-utils-3.0.21.jar"],
)

java_import(
    name = "protobuf",
    jars = ["protobuf/protobuf-java-3.0.0-alpha-3.jar"],
)

# For bootstrapping JavaBuilder
filegroup(
    name = "protobuf-jars",
    srcs = ["protobuf/protobuf-java-3.0.0-alpha-3.jar"],
)

java_import(
    name = "slf4j",
    jars = [
        "slf4j/slf4j-api-1.7.7.jar",
        "slf4j/slf4j-jdk14-1.7.7.jar",
    ],
)

java_import(
    name = "tomcat_annotations_api",
    jars = ["tomcat_annotations_api/tomcat-annotations-api-8.0.5.jar"],
)

# Testing

java_import(
    name = "guava-testlib",
    jars = ["guava/guava-testlib.jar"],
)

java_import(
    name = "junit4",
    jars = [
        "hamcrest/hamcrest-core-1.3.jar",
        "junit/junit-4.11.jar",
    ],
)

java_import(
    name = "mockito",
    jars = ["mockito/mockito-all-1.10.19.jar"],
)

java_import(
    name = "truth",
    jars = ["truth/truth-0.27.jar"],
)

cc_library(
    name = "gtest",
    srcs = [
        "gtest/gtest-all.cc",
        "gtest/gtest_main.cc",
    ],
    hdrs = [
        "gtest/gtest.h",
    ],
    data = [
        "//tools:test_sharding_compliant",
    ],
    includes = ["."],
    # gtest detects pthread, and the linker fails without it.
    linkopts = ["-lpthread"],
)

# To be used by the skylark example.
filegroup(
    name = "junit4-jars",
    srcs = [
        "hamcrest/hamcrest-core-1.3.jar",
        "junit/junit-4.11.jar",
    ],
)

config_setting(
    name = "windows_mingw",
    values = {"compiler": "windows_mingw"},
)

config_setting(
    name = "windows_msys64_mingw64",
    values = {"compiler": "windows_msys64_mingw64"},
)

config_setting(
    name = "windows_clang",
    values = {"compiler": "windows_clang"},
)

config_setting(
    name = "darwin",
    values = {"host_cpu": "darwin"},
)

config_setting(
    name = "k8",
    values = {"host_cpu": "k8"},
)

config_setting(
    name = "piii",
    values = {"host_cpu": "piii"},
)

config_setting(
    name = "arm",
    values = {"host_cpu": "arm"},
)

config_setting(
    name = "freebsd",
    values = {"host_cpu": "freebsd"},
)
