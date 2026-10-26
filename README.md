# HL7 Australia Sample FHIR implementation guide

This repository contains a sample FHIR Implementation Guide (IG) for learning how to create, build, validate and maintain FHIR IGs using the HL7 FHIR IG Publisher.

The sample includes a basic IG structure, configuratio files, example FHIR artefacts and narrative pages that can be used to explore how an IG works or as a starting point for developing your own IG.

This is a sample for learning and development, not an implementation specification.

## Getting started
To work with the sample IG, you will need to install the required tools, download the repository and build the IG locally.

**1. Install the required tools**

Before building the sample IG, make sure you have:

- Java JDK (64-bit, minimum Java 11) – runs the IG Publisher.
- Git – downloads the repository and tracks changes.
- Ruby and Jekyll – generate the IG website.
- A text editor – such as Visual Studio Code, for editing the IG files.

SUSHI is not required for this sample IG, as the FHIR artefacts are authored in XML or JSON rather than FHIR Shorthand (FSH).

For installation instructions, see the [Confluence setup](https://confluence.hl7.org/spaces/HAFWG/pages/498542948/Setting+Up+Your+IG+Authoring+Environment) page.

**2. Get the sample IG repository**

You can clone the repository to your computer:

`git clone https://github.com/hl7au/sample-ig.git`

`cd sample-ig`

Alternatively, you can fork the repository to your own GitHub account and clone your fork.

See the [Confluence setup](https://confluence.hl7.org/spaces/HAFWG/pages/498542948/Setting+Up+Your+IG+Authoring+Environment) page for instructions on cloning and forking.

**3. Build the sample IG**

From the repository directory, download or update the IG Publisher using the supplied script.

Windows:

`_updatePublisher.bat`

`_genonce.bat`

macOS/Linux:

`./_updatePublisher.sh`

`./_genonce.sh`

The first build may take several minutes while the Publisher downloads the required packages and dependencies.

Once the build completes, open:

- `output/index.html` – the generated IG website.
- `output/qa.html` – the QA report containing validation errors, warnings and informational messages.

For more information about the build process, see the [Confluence setup](https://confluence.hl7.org/spaces/HAFWG/pages/498542948/Setting+Up+Your+IG+Authoring+Environment) page.

## Repository structure
The repository contains the source files, configuration and scripts used to build the sample IG.

```
├── ig.ini                       # Configuration file used to start the IG Publisher; points at the IG resource and template
├── input/                       # Contains the IG source files   
│   ├── ig.xml                   # The ImplementationGuide resource; defines the IG metadata, dependencies, resources and pages
│   ├── resources/               # FHIR artefacts, such as profiles, extensions, value sets, code systems, etc
│   ├── examples/                # Example FHIR resource instances
│   ├── pagecontent/             # Narrative pages, writen in Markdown or XML
│   ├── intro-notes/             # Optional text added to the top or bottom of artifact pages
│   ├── images/                  # Images and diagrams used in the IG pages
│   ├── includes/                # Reusable snippets (advanced)
│   └── ignoreWarnings.txt       # Optional file used to document and suppress selected QA warnings
├── _updatePublisher.bat/.sh     # Downloads or updates the IG Publisher
├── _genonce.bat/.sh             # Runs a full IG build
├── _gencontinuous.bat/.sh       # Rebuilds the IG when source changes
├── input-cache/                 # Stores the downloaded IG Publisher (publisher.jar) and cached files
├── output/                      # Contains the generated IG website and QA report
└── temp/                        # Temporary files generated during the build
└── template/                    # Template files used to generate the IG
└── README.md                    # Information about using this repository
```

The exact structure may vary depending on the IG configuration.

## Using the sample IG for your own project
You can use this repository as a starting point for creating your own FHIR IG.

Once you have copied the repository, you will need to:

1. **Update the IG configuration** - change the IG identifiers, canonical URL, package ID, title, publisher, version and other project information.
2. **Review dependencies** - update the FHIR version and dependencies as needed.
3. **Replace the sample content** - remove or modify the sample FHIR artefacts, examples and narrative pages.
4. **Update the IG resource and navigation** – make sure the ImplementationGuide resource includes the correct resources and pages.
5. **Build and validate** - run the IG Publisher and review the generated website and QA report.

Do not retain the sample IG's canonical URL or package ID when creating a new IG. These must be appropriate for your project.


## Further information

- [FHIR R4 specification](https://hl7.org/fhir/R4/)
- [FHIR Profiling](https://hl7.org/fhir/R4/profiling.html)
- [FHIR Implementation Guide resource](https://hl7.org/fhir/R4/implementationguide.html)
- [FHIR IG Publisher documentation](https://confluence.hl7.org/spaces/FHIR/pages/35718627/IG+Publisher+Documentation)
- [Guidance for FHIR IG Creation](https://build.fhir.org/ig/FHIR/ig-guidance/)
- [HL7 Australia GitHub organisation](https://github.com/hl7au)
- [FHIR chat - Zulip](https://chat.fhir.org/)

## Feedback and issues

If you've found an issue with this repository or it's contents, please [raise a GitHub issue](https://github.com/hl7au/sample-ig/issues).