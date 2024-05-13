# GLayout - Hierarchical Layout Design Platform

## Background & Motivation

Open source development in the field of electronic design automation (EDA) provides a collaborative foundation for advancing integrated circuit (IC) design methodologies. The OpenFASOC framework has been instrumental in fostering this development, offering tools and templates for digital and analog circuit design.

While the template approach employed in some other analog generators yields high quality results, it also comes with its limitations. The templates can be restrictive when it comes to customizing highly specific layout patterns, which are crucial in advanced analog design.

## Introduction to GLayout

GLayout emerges as a solution to bridge the gap, offering a hierarchical layout platform that empowers the user to specify and manipulate layouts with a high degree of detail. One of the core components of GLayout is the Mapped PDK (Process Design Kit), which translates foundry-specific technology files into an accessible and programmable interface.

### Key Features of GLayout

- **Hierarchical Layout Generation**: Allows complex layout structures with varying levels of abstraction.
- **High-Level Detail Specificity**: Enables detailed feature placement and routing.
- **Mapped PDK**: Incorporates a flexible foundation applicable accross technology nodes for complete code reuse.

## Implementation Basics

GLayout is built around two primary constructs: Glayers and Grules.

- **Glayers (Generic Layers)**: These abstract representations of physical layers (e.g., metals, vias) in the IC process are mapped to foundry-specific layers through the Mapped PDK.
- **Grules (Generic Rules)**: These encapsulate the design rules associated with layers, such as spacing, width, and enclosure, ensuring that the generated layout adheres to manufacturing constraints.

## Examples and Walkthrough

### Example 1: Via Generation and Rule Understanding

The first example dives into the foundation of layout creation, explaining how to interact with Glayers and Grules. It demonstrates the process of defining a via between different metal layers, considering the rules like minimum width and spacing from the PDK.

```python
# Via generation code snippet
def create_via(PDK):
    via_layer = PDK.get_generic_layer('via')
    metal1_layer = PDK.get_generic_layer('metal1')
    # ... additional implementation details ...
    return via_component
```

### Example 2: Place and Routing Macros with a Current Mirror

The second example builds upon the first by introducing more complex place and route operations. It dives into the explicit placement and routing of a PMOS current mirror circuit, showcasing how design elements can be controlled at a granular level.

```python
# Current mirror placement and routing code snippet
def currentMirror(pdk: MappedPDK):
    # ... initialization and transistor placement ...
    currMirrComp << straight_route(pdk, source_port, mirror_port)
    # ... additional place and route details ...
    return currMirrComp
```

### Macro Place and Route

With GLayout, users also have the option to harness macros for placing and routing, simplifying repeated patterns and structures in the layout.
