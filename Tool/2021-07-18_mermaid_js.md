# Mermaid

## [About Mermaid](https://mermaid-js.github.io/mermaid/#/README)

**Mermaid lets you create diagrams and visualizations using text and code.**

It is a Javascript based diagramming and charting tool that renders Markdown-inspired text definitions to create and modify diagrams dynamically.

[Typora-Draw Diagrams With Markdown](https://support.typora.io/Draw-Diagrams-With-Markdown/)

## Diagrams

- Sequence Diagrams: `sequenceDiagram`
- Flowcharts: `graph LR`
- Class Diagrams: `classDiagram`
- State Diagrams: `stateDiagram`
- Gantt Charts: `gantt`
- Pie Charts: `pie`

```mermaid
pie
title Mermaid diagrams
"sequenceDiagram" : 1
"graph LR" : 1
"classDiagram" : 1
"stateDiagram" : 1
"gantt" : 1
"pie" : 1
```

## Sequence Diagrams

Label: `sequenceDiagram`

A sequence diagram is **a type of interaction diagram** because it describes how—and in what order—a group of objects works together. These diagrams are used by software developers and business professionals to understand requirements for a new system or to document an existing process.

```
sequenceDiagram
participant Alice
participant John
participant Bob
autonumber
Alice->>John: Hello John, how are you?

%% loop example
  loop Healthcheck
  John->>John: Fight against hypochondria
  end

%% Note Example
	Note right of John: Rational thoughts!

John-->>Alice: Great!
John->>Bob: How about you?
activate Bob
Bob-->>John: Jolly good!
deactivate Bob

%% Alt Example
  Alice->>Bob: Hello Bob, how are you?
  alt is sick
  Bob->>Alice: Not so good :(
  else is well
  Bob->>Alice: Feeling fresh like a daisy
  end
  opt Extra response
  Bob->>Alice: Thanks for asking
  end
  
%% Paraller example
  par [Alice To Bob]
  Alice->>Bob: How about you?
  and [Alice To John]
  Alice->>John: How about you?
  end

%% Entity codes to escape characters
  Alice->>Bob: I #9829; you!
  Bob-->>Alice: I #9829; you 3000 more!
```

```mermaid
sequenceDiagram
participant Alice
participant John
participant Bob
autonumber
Alice->>John: Hello John, how are you?

%% loop example
  loop Healthcheck
  John->>John: Fight against hypochondria
  end

%% Note Example
	Note right of John: Rational thoughts!

John-->>Alice: Great!
John->>Bob: How about you?
activate Bob
Bob-->>John: Jolly good!
deactivate Bob

%% Alt Example
  Alice->>Bob: Hello Bob, how are you?
  alt is sick
  Bob->>Alice: Not so good :(
  else is well
  Bob->>Alice: Feeling fresh like a daisy
  end
  opt Extra response
  Bob->>Alice: Thanks for asking
  end
  
%% Paraller example
  par [Alice To Bob]
  Alice->>Bob: How about you?
  and [Alice To John]
  Alice->>John: How about you?
  end

%% Entity codes to escape characters
  Alice->>Bob: I #9829; you!
  Bob-->>Alice: I #9829; you 3000 more!
```

### Basic symbols and components

To understand what a sequence diagram is, you should be familiar with its symbols and components. Sequence diagrams are made up of the following icons and elements:

| Symbol                                                       | Name               | Description                                                  |
| ------------------------------------------------------------ | ------------------ | ------------------------------------------------------------ |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718223931768.png" alt="image-20210718223931768" style="zoom:50%;" /> | Object symbol      | Represents a class or object in UML. The object symbol demonstrates how an object will behave in the context of the system. Class attributes should not be listed in this shape. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718224037649.png" alt="image-20210718224037649" style="zoom:25%;" /> | Activation box     | Represents the time needed for an object to complete a task. The longer the task will take, the longer the activation box becomes. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718225845565.png" alt="image-20210718225845565" style="zoom: 25%;" /> | Actor symbol       | Shows entities that interact with or are external to the system. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718225945776.png" alt="image-20210718225945776" style="zoom:25%;" /> | Package symbol     | Used in UML 2.0 notation to contain interactive elements of the diagram. Also known as a frame, this rectangular shape has a small inner rectangle for labeling the diagram. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230022493.png" alt="image-20210718230022493" style="zoom:25%;" /> | Lifeline symbol    | Represents the passage of time as it extends downward. This dashed vertical line shows the sequential events that occur to an object during the charted process. Lifelines may begin with a labeled rectangle shape or an actor symbol. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230109725.png" alt="image-20210718230109725" style="zoom:25%;" /> | Option loop symbol | Used to model if/then scenarios, i.e., a circumstance that will only occur under certain conditions. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230151597.png" alt="image-20210718230151597" style="zoom:25%;" /> | Alternative symbol | Symbolizes a choice (that is usually mutually exclusive) between two or more message sequences. To represent alternatives, use the labeled rectangle shape with a dashed line inside. |

### Common message symbols

Use the following arrows and message symbols to show how information is transmitted between objects. These symbols may reflect the start and execution of an operation or the sending and reception of a signal.

| Symbol                                                       | Name                               | Description                                                  |
| ------------------------------------------------------------ | ---------------------------------- | ------------------------------------------------------------ |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230415544.png" alt="image-20210718230415544" style="zoom:50%;" /> | Synchronous message symbol         | Represented by a solid line with a solid arrowhead. This symbol is used when a sender must wait for a response to a message before it continues. The diagram should show both the call and the reply. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230603322.png" alt="image-20210718230603322" style="zoom:50%;" /> | Asynchronous message symbol        | Represented by a solid line with a lined arrowhead. Asynchronous messages don't require a response before the sender continues. Only the call should be included in the diagram. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230653044.png" alt="image-20210718230653044" style="zoom:50%;" /> | Asynchronous return message symbol | Represented by a dashed line with a lined arrowhead.         |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230716909.png" alt="image-20210718230716909" style="zoom:50%;" /> | Asynchronous create message symbol | Represented by a dashed line with a lined arrowhead. This message creates a new object. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230802350.png" alt="image-20210718230802350" style="zoom:50%;" /> | Reply message symbol               | Represented by a dashed line with a lined arrowhead, these messages are replies to calls. |
| <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718230842132.png" alt="image-20210718230842132" style="zoom:50%;" /> | Delete message symbol              | Represented by a solid line with a solid arrowhead, followed by an X. This message destroys an object. |

There are six types of arrows currently supported:

| Type | Description                                      |
| ---- | ------------------------------------------------ |
| ->   | Solid line without arrow                         |
| -->  | Dotted line without arrow                        |
| ->>  | Solid line with arrowhead                        |
| -->> | Dotted line with arrowhead                       |
| -x   | Solid line with a cross at the end               |
| --x  | Dotted line with a cross at the end.             |
| -)   | Solid line with an open arrow at the end (async) |
| --)  | Dotted line with a open arrow at the end (async) |

## Flowcharts

Label: `graph LR`

Possible FlowChart orientations are:

- TB - top to bottom
- TD - top-down/ same as top to bottom
- BT - bottom to top
- RL - right to left
- LR - left to right

```
graph LR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

```mermaid
graph LR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

Learn more at: [Mermaid - Flowchart](https://mermaid-js.github.io/mermaid/#/flowchart)

### Most used flow chart symbols

| Meaning                      | Symbols                                                      |
| ---------------------------- | ------------------------------------------------------------ |
| Terminal/Terminator          | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233350723.png" alt="image-20210718233350723" style="zoom:25%;" /> |
| Process                      | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233417189.png" alt="image-20210718233417189" style="zoom:25%;" /> |
| Decision                     | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233435101.png" alt="image-20210718233435101" style="zoom:25%;" /> |
| Document                     | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233451459.png" alt="image-20210718233451459" style="zoom:25%;" /> |
| Data, or Input/Output        | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233508761.png" alt="image-20210718233508761" style="zoom:25%;" /> |
| Stored Data                  | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233524817.png" alt="image-20210718233524817" style="zoom:25%;" /> |
| Flow Arrow                   | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233542867.png" alt="image-20210718233542867" style="zoom:25%;" /> |
| Comment or Annotation        | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233642252.png" alt="image-20210718233642252" style="zoom:25%;" /> |
| Predefined process           | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233704270.png" alt="image-20210718233704270" style="zoom:25%;" /> |
| On-page connector/reference  | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233601104.png" alt="image-20210718233601104" style="zoom:25%;" /> |
| Off-page connector/reference | <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/image-20210718233721038.png" alt="image-20210718233721038" style="zoom:25%;" /> |

### Common flowchart symbols

| Flowchart Symbol                                             | Name                           | Description                                                  |
| :----------------------------------------------------------- | :----------------------------- | :----------------------------------------------------------- |
| ![Process Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/process_symbol-60x45.PNG) | Process symbol                 | Also known as an “Action Symbol,” this shape represents a process, action, or function. It’s the most widely-used symbol in flowcharting. |
| ![Start/End Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/terminator_symbol-60x31.PNG) | Start/End symbol               | Also known as the “Terminator Symbol,” this symbol represents the start points, end points, and potential outcomes of a path. Often contains “Start” or “End” within the shape. |
| ![Document Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/document_symbol-60x46.PNG) | Document symbol                | Represents the input or output of a document, specifically. Examples of and input are receiving a report, email, or order. Examples of an output using a document symbol include generating a presentation, memo, or letter. |
| ![Decision Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/decision_symbol-60x46.PNG) | Decision symbol                | Indicates a question to be answered — usually yes/no or true/false. The flowchart path may then split off into different branches depending on the answer or consequences thereafter. |
| ![Connector Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/connector_symbol-60x40.PNG) | Connector symbol               | Usually used within more complex charts, this symbol connects separate elements across one page. |
| ![Off-page Connector Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/offpage_connector-60x50.PNG) | Off-Page Connector/Link symbol | Frequently used within complex charts, this symbol connects separate elements across multiple pages with the page number usually placed on or within the shape for easy reference. |
| ![Input/Output Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/data_symbol-60x46.PNG) | Input/Output symbol            | Also referred to as the “Data Symbol,” this shape represents data that is available for input or output as well as representing resources used or generated. While the paper tape symbol also represents input/output, it is outdated and no longer in common use for flowchart diagramming. |
| ![Comment Flowchart Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/note_symbol-60x80.PNG) | Comment/Note symbol            | Placed along with context, this symbol adds needed explanation or comments within the specified range. It may be connected by a dashed line to the relevant section of the flowchart as well. |

### Additional flowchart symbols

Many of these additional flowchart symbols are best utilized when mapping out a process flow diagram for apps, user flow, data processing, etc.

| Flowchart Symbol                                             | Name                      | Description                                                  |
| :----------------------------------------------------------- | :------------------------ | :----------------------------------------------------------- |
| ![Database Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/stored_data_symbol-60x60.PNG) | Database symbol           | Represents data housed on a storage service that will likely allow for searching and filtering by users. |
| ![Paper Tape Symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/paper-tape-flowchart-symbol.png) | Paper tape symbol         | An outdated symbol rarely ever used in modern practices or process flows, but this shape could be used if you’re mapping out processes or input methods on much older computers and CNC machines. |
| ![Summing junction symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/summing_junction_symbol-60x37.PNG) | Summing junction symbol   | Sums the input of several converging paths.                  |
| ![predefined process symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/predefined_process_symbol-60x45.PNG) | Predefined process symbol | Indicates a complicated process or operation that is well-known or defined elsewhere. |
| ![internal storage symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/internal-storage-flowchart-symbol.png) | Internal storage symbol   | Commonly used to map out software designs, this shape indicates data that is stored within internal memory. |
| ![manual input symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/manual_input_symbol-60x45.PNG) | Manual input symbol       | Represents the manual input of data into a field or step in a process, usually through a keyboard or device. Example scenario includes the step in a login process where a user is prompted to enter data manually. |
| ![manual operation symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/manual_operation_symbol-60x46.PNG) | Manual operation symbol   | Indicates a step that must be done manually, not automatically. |
| ![merge symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/merge_symbol-60x46.PNG) | Merge symbol              | Combines multiple paths to become one.                       |
| ![multiple documents symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/multiple_documents_symbol-60x46.PNG) | Multiple documents symbol | Represents multiple documents or reports.                    |
| ![preparation symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/flowchart-symbols-meaning-explained/preparation_symbol-60x46.PNG) | Preparation symbol        | Differentiates between steps that prepare for work and steps that actually do work. It helps introduce the setup to another step within the same process. |
| ![stored data symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/stored-data-symbol.png) | Stored data symbol        | Also known as “Data Storage” symbol, this shape represents where data gets stored within a process. |
| ![delay symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/delay-flowchart-symbol.png) | Delay symbol              | Represents a segment of delay in a process. It can be helpful to indicate the exact length of delay within the shape. |
| ![or symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/or-flowchart-symbol.png) | Or symbol                 | Just as described, this shape indicates that the process flow continues two paths or more. |
| ![display symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/display-flowchart-symbol.png) | Display symbol            | This shape is useful to indicate where information will get displayed within a process flow. |
| ![hard disk symbol](https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/examples/hard-disk-flowchart-symbol.png) | Hard disk symbol          | Indicates where data is stored within a hard drive, also known as direct access storage. |



## Class Diagrams

Label: `classDiagram`

## Gantt Charts

Label: `gantt`

## Pie Charts

Label: `pie`

## References

- [UML Sequence Diagram Tutorial](https://www.lucidchart.com/pages/uml-sequence-diagram)
- [What is Flowchart](https://www.lucidchart.com/pages/what-is-a-flowchart-tutorial/#section_3)
- [Flowchart Symbols and Notation](https://www.lucidchart.com/pages/flowchart-symbols-meaning-explained/#section_2)
- [Mermaid Diagram Syntax](https://mermaid-js.github.io/mermaid/#/)