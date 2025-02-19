---
title: dartanalyzer configuration in MegaLinter
description: How to use dartanalyzer (configure, ignore files, ignore errors, help & version documentations) to analyze DART files
---
<!-- markdownlint-disable MD033 MD041 -->
<!-- @generated by .automation/build.py, please don't update manually -->

<div align="center">
  <a href="https://github.com/dart-lang/sdk/tree/master/pkg/analyzer_cli#readme" target="blank" title="Visit linter Web Site">
    <img src="https://manifesto.co.uk/wp-content/uploads/2014/08/dart-logo.png" alt="dartanalyzer" height="150px" class="megalinter-banner">
  </a>
</div>

![downgraded version](https://shields.io/badge/-downgraded%20version-orange) [![GitHub stars](https://img.shields.io/github/stars/dart-lang/sdk?cacheSeconds=3600)](https://github.com/dart-lang/sdk) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/dart-lang/sdk?sort=semver)](https://github.com/dart-lang/sdk/releases) [![GitHub last commit](https://img.shields.io/github/last-commit/dart-lang/sdk)](https://github.com/dart-lang/sdk/commits) [![GitHub commit activity](https://img.shields.io/github/commit-activity/y/dart-lang/sdk)](https://github.com/dart-lang/sdk/graphs/commit-activity/) [![GitHub contributors](https://img.shields.io/github/contributors/dart-lang/sdk)](https://github.com/dart-lang/sdk/graphs/contributors/)

## dartanalyzer documentation

- Visit [Official Web Site](https://github.com/dart-lang/sdk/tree/master/pkg/analyzer_cli#readme){target=_blank}
- See [How to configure dartanalyzer rules](https://dart.dev/guides/language/analysis-options#the-analysis-options-file){target=_blank}
  - If custom `analysis_options.yml` config file isn't found, [analysis_options.yml](https://github.com/oxsecurity/megalinter/tree/main/TEMPLATES/analysis_options.yml){target=_blank} will be used
- See [How to disable dartanalyzer rules in files](https://dart.dev/guides/language/analysis-options#suppressing-rules-for-a-file){target=_blank}

[![sdk - GitHub](https://gh-card.dev/repos/dart-lang/sdk.svg?fullname=)](https://github.com/dart-lang/sdk){target=_blank}

## Configuration in MegaLinter

- Enable dartanalyzer by adding `DART_DARTANALYZER` in [ENABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)
- Disable dartanalyzer by adding `DART_DARTANALYZER` in [DISABLE_LINTERS variable](https://megalinter.io/beta/configuration/#activation-and-deactivation)

| Variable                                      | Description                                                                                                                                                                                  | Default value                                   |
|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| DART_DARTANALYZER_ARGUMENTS                   | User custom arguments to add in linter CLI call<br/>Ex: `-s --foo "bar"`                                                                                                                     |                                                 |
| DART_DARTANALYZER_COMMAND_REMOVE_ARGUMENTS    | User custom arguments to remove from command line before calling the linter<br/>Ex: `-s --foo "bar"`                                                                                         |                                                 |
| DART_DARTANALYZER_FILTER_REGEX_INCLUDE        | Custom regex including filter<br/>Ex: `(src\|lib)`                                                                                                                                           | Include every file                              |
| DART_DARTANALYZER_FILTER_REGEX_EXCLUDE        | Custom regex excluding filter<br/>Ex: `(test\|examples)`                                                                                                                                     | Exclude no file                                 |
| DART_DARTANALYZER_CLI_LINT_MODE               | Override default CLI lint mode<br/>- `file`: Calls the linter for each file<br/>- `project`: Call the linter from the root of the project                                                    | `file`                                          |
| DART_DARTANALYZER_FILE_EXTENSIONS             | Allowed file extensions. `"*"` matches any extension, `""` matches empty extension. Empty list excludes all files<br/>Ex: `[".py", ""]`                                                      | `[".dart"]`                                     |
| DART_DARTANALYZER_FILE_NAMES_REGEX            | File name regex filters. Regular expression list for filtering files by their base names using regex full match. Empty list includes all files<br/>Ex: `["Dockerfile(-.+)?", "Jenkinsfile"]` | Include every file                              |
| DART_DARTANALYZER_PRE_COMMANDS                | List of bash commands to run before the linter                                                                                                                                               | None                                            |
| DART_DARTANALYZER_POST_COMMANDS               | List of bash commands to run after the linter                                                                                                                                                | None                                            |
| DART_DARTANALYZER_UNSECURED_ENV_VARIABLES     | List of env variables explicitly not filtered before calling DART_DARTANALYZER and its pre/post commands                                                                                     | None                                            |
| DART_DARTANALYZER_CONFIG_FILE                 | dartanalyzer configuration file name</br>Use `LINTER_DEFAULT` to let the linter find it                                                                                                      | `analysis_options.yml`                          |
| DART_DARTANALYZER_RULES_PATH                  | Path where to find linter configuration file                                                                                                                                                 | Workspace folder, then MegaLinter default rules |
| DART_DARTANALYZER_DISABLE_ERRORS              | Run linter but consider errors as warnings                                                                                                                                                   | `false`                                         |
| DART_DARTANALYZER_DISABLE_ERRORS_IF_LESS_THAN | Maximum number of errors allowed                                                                                                                                                             | `0`                                             |
| DART_DARTANALYZER_CLI_EXECUTABLE              | Override CLI executable                                                                                                                                                                      | `['dartanalyzer']`                              |

## IDE Integration

Use dartanalyzer in your favorite IDE to catch errors before MegaLinter !

|                                                                  <!-- -->                                                                   | IDE                                                      | Extension Name                                                                       |                                                                                 Install                                                                                  |
|:-------------------------------------------------------------------------------------------------------------------------------------------:|----------------------------------------------------------|--------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|  <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/idea.ico" alt="" height="32px" class="megalinter-icon"></a>  | [IDEA](https://www.jetbrains.com/products.html#type=ide) | [dart-jetbrains-plugin](https://plugins.jetbrains.com/plugin/6351-dart)              |                       <iframe frameborder="none" width="245px" height="48px" src="https://plugins.jetbrains.com/embeddable/install/6351"></iframe>                       |
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/icons/vscode.ico" alt="" height="32px" class="megalinter-icon"></a> | [Visual Studio Code](https://code.visualstudio.com/)     | [dart-code](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code) | [![Install in VSCode](https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/btn_install_vscode.png)](vscode:extension/Dart-Code.dart-code){target=_blank} |

## MegaLinter Flavours

This linter is available in the following flavours

|                                                                         <!-- -->                                                                         | Flavor                                               | Description               | Embedded linters |                                                                                                                                                                       Info |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------|:--------------------------|:----------------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| <img src="https://github.com/oxsecurity/megalinter/raw/main/docs/assets/images/mega-linter-square.png" alt="" height="32px" class="megalinter-icon"></a> | [all](https://megalinter.io/beta/supported-linters/) | Default MegaLinter Flavor |       118        | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/oxsecurity/megalinter/beta) ![Docker Pulls](https://img.shields.io/docker/pulls/oxsecurity/megalinter) |

## Behind the scenes

### How are identified applicable files

- File extensions: `.dart`

<!-- markdownlint-disable -->
<!-- /* cSpell:disable */ -->
### How the linting is performed

- dartanalyzer is called one time by identified file (`file` CLI lint mode)

### Example calls

```shell
dartanalyzer --fatal-infos --fatal-warnings myfile.dart
```

```shell
dartanalyzer --fatal-infos --fatal-warnings --options analysis_options.yml myfile.dart
```


### Help content

```shell
Usage: dartanalyzer [options...] <directory or list of files>

    --dart-sdk                    The path to the Dart SDK.
    --options                     Path to an analysis options file.
    --package-root                The path to a package root directory (deprecated). This option cannot be used with --packages.
    --[no-]declaration-casts      Disable declaration casts in strong mode (https://goo.gl/cTLz40)
                                  This option is now ignored and will be removed in a future release.
    --[no-]implicit-casts         Disable implicit casts in strong mode (https://goo.gl/cTLz40).
    --no-implicit-dynamic         Disable implicit dynamic (https://goo.gl/m0UgXD).
    --packages                    The path to the package resolution configuration file, which supplies a mapping of package names
                                  to paths. This option cannot be used with --package-root.
    --[no-]lints                  Show lint results.
    --format                      Specifies the format in which errors are displayed; the only currently allowed value is 'machine'.
    --version                     Print the analyzer version.
    --enable-experiment           Enable one or more experimental features. If multiple features are being added, they should be comma separated.
    --no-hints                    Do not show hint results.
    --fatal-infos                 Treat infos as fatal.
    --fatal-warnings              Treat non-type warnings as fatal.
-h, --help                        Display this help message. Add --verbose to show hidden options.
-v, --verbose                     Verbose output.
    --default-language-version    The default language version when it is not specified via other ways (internal, tests only).

Run "dartanalyzer -h -v" for verbose help output, including less commonly used options.
For more information, see https://www.dartlang.org/tools/analyzer.

```

### Installation on mega-linter Docker image

- Dockerfile commands :
```dockerfile
# Parent descriptor install
ENV LANG=C.UTF-8
RUN ALPINE_GLIBC_BASE_URL="https://github.com/sgerrand/alpine-pkg-glibc/releases/download" && \
    ALPINE_GLIBC_PACKAGE_VERSION="2.34-r0" && \
    ALPINE_GLIBC_BASE_PACKAGE_FILENAME="glibc-$ALPINE_GLIBC_PACKAGE_VERSION.apk" && \
    ALPINE_GLIBC_BIN_PACKAGE_FILENAME="glibc-bin-$ALPINE_GLIBC_PACKAGE_VERSION.apk" && \
    ALPINE_GLIBC_I18N_PACKAGE_FILENAME="glibc-i18n-$ALPINE_GLIBC_PACKAGE_VERSION.apk" && \
    apk add --no-cache --virtual=.build-dependencies wget ca-certificates && \
    echo \
        "-----BEGIN PUBLIC KEY-----\
        MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEApZ2u1KJKUu/fW4A25y9m\
        y70AGEa/J3Wi5ibNVGNn1gT1r0VfgeWd0pUybS4UmcHdiNzxJPgoWQhV2SSW1JYu\
        tOqKZF5QSN6X937PTUpNBjUvLtTQ1ve1fp39uf/lEXPpFpOPL88LKnDBgbh7wkCp\
        m2KzLVGChf83MS0ShL6G9EQIAUxLm99VpgRjwqTQ/KfzGtpke1wqws4au0Ab4qPY\
        KXvMLSPLUp7cfulWvhmZSegr5AdhNw5KNizPqCJT8ZrGvgHypXyiFvvAH5YRtSsc\
        Zvo9GI2e2MaZyo9/lvb+LbLEJZKEQckqRj4P26gmASrZEPStwc+yqy1ShHLA0j6m\
        1QIDAQAB\
        -----END PUBLIC KEY-----" | sed 's/   */\\n/g' > "/etc/apk/keys/sgerrand.rsa.pub" && \
    wget --quiet --tries=10 --waitretry=10 \
        "$ALPINE_GLIBC_BASE_URL/$ALPINE_GLIBC_PACKAGE_VERSION/$ALPINE_GLIBC_BASE_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_BASE_URL/$ALPINE_GLIBC_PACKAGE_VERSION/$ALPINE_GLIBC_BIN_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_BASE_URL/$ALPINE_GLIBC_PACKAGE_VERSION/$ALPINE_GLIBC_I18N_PACKAGE_FILENAME" && \
    mv /etc/nsswitch.conf /etc/nsswitch.conf.bak && \
    apk add --no-cache --force-overwrite \
        "$ALPINE_GLIBC_BASE_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_BIN_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_I18N_PACKAGE_FILENAME" && \
    \
    mv /etc/nsswitch.conf.bak /etc/nsswitch.conf && \
    rm "/etc/apk/keys/sgerrand.rsa.pub" && \
    (/usr/glibc-compat/bin/localedef --force --inputfile POSIX --charmap UTF-8 "$LANG" || true) && \
    echo "export LANG=$LANG" > /etc/profile.d/locale.sh && \
    \
    apk del glibc-i18n && \
    \
    rm "/root/.wget-hsts" && \
    apk del .build-dependencies && \
    rm \
        "$ALPINE_GLIBC_BASE_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_BIN_PACKAGE_FILENAME" \
        "$ALPINE_GLIBC_I18N_PACKAGE_FILENAME"

# Linter install
ARG DART_VERSION='2.8.4'
RUN wget --tries=5 https://storage.googleapis.com/dart-archive/channels/stable/release/${DART_VERSION}/sdk/dartsdk-linux-x64-release.zip -O - -q | unzip -q - \
    && chmod +x dart-sdk/bin/dart* \
    && mv dart-sdk/bin/* /usr/bin/ && mv dart-sdk/lib/* /usr/lib/ && mv dart-sdk/include/* /usr/include/ \
    && rm -r dart-sdk/

```

