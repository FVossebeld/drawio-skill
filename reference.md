# draw.io XML Reference

## Azure Icon Library

draw.io has built-in Azure icons at `img/lib/azure2/`. Use these for professional diagrams:

### Icon Paths by Category

| Category | Path | Example Icons |
|----------|------|---------------|
| **Compute** | `img/lib/azure2/compute/` | `App_Services.svg`, `Function_Apps.svg`, `Virtual_Machine.svg`, `Kubernetes_Services.svg` |
| **Databases** | `img/lib/azure2/databases/` | `SQL_Database.svg`, `Azure_Cosmos_DB.svg`, `Cache_Redis.svg` |
| **Networking** | `img/lib/azure2/networking/` | `Front_Doors.svg`, `DNS_Zones.svg`, `Virtual_Networks.svg`, `Application_Gateways.svg` |
| **Identity** | `img/lib/azure2/identity/` | `Azure_Active_Directory.svg`, `Managed_Identities.svg` |
| **AI + ML** | `img/lib/azure2/ai_machine_learning/` | `Azure_OpenAI.svg`, `Cognitive_Services.svg`, `Machine_Learning.svg` |
| **Analytics** | `img/lib/azure2/analytics/` | `Log_Analytics_Workspaces.svg`, `Event_Hubs.svg` |
| **Integration** | `img/lib/azure2/integration/` | `Service_Bus.svg`, `Event_Grid_Domains.svg`, `Logic_Apps.svg` |
| **Management** | `img/lib/azure2/management_governance/` | `Monitor.svg`, `Policy.svg` |
| **Security** | `img/lib/azure2/security/` | `Key_Vaults.svg`, `Azure_Defender.svg` |
| **Storage** | `img/lib/azure2/storage/` | `Storage_Accounts.svg` |
| **App Services** | `img/lib/azure2/app_services/` | `Search_Services.svg`, `API_Management_Services.svg` |
| **General** | `img/lib/azure2/general/` | `Resource_Groups.svg`, `File.svg` |

### Icon Cell Template

```xml
<!-- Azure icon with label below -->
<mxCell id="app-service" value="Web App"
  style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/App_Services.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="64" height="64" as="geometry" />
</mxCell>

<!-- Azure icon with label above -->
<mxCell id="front-door" value="Azure Front Door&#xa;WAF&#xa;CDN"
  style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/networking/Front_Doors.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="68" height="60" as="geometry" />
</mxCell>
```

### Built-in Azure Shapes (non-icon)

```xml
<!-- Queue (Azure storage queue shape) -->
<mxCell id="queue" value="Queue"
  style="verticalLabelPosition=top;html=1;verticalAlign=bottom;align=center;strokeColor=none;fillColor=#00BEF2;shape=mxgraph.azure.storage_queue;labelPosition=center;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="50" height="45" as="geometry" />
</mxCell>

<!-- Blob Storage (Azure blob shape) -->
<mxCell id="blob" value="Blob"
  style="verticalLabelPosition=bottom;html=1;verticalAlign=top;align=center;strokeColor=none;fillColor=#00BEF2;shape=mxgraph.azure.storage_blob;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="50" height="45" as="geometry" />
</mxCell>
```

---

## Grouping & Container Patterns

Enterprise diagrams use container patterns for logical grouping:

### Resource Group Boundary (Outer Dashed Container)

```xml
<!-- Outer boundary for entire resource group / subscription -->
<mxCell id="rg-boundary" value=""
  style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;dashed=1;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="160" y="40" width="800" height="400" as="geometry" />
</mxCell>

<!-- Resource group label (small icon) -->
<mxCell id="rg-label" value="Resource Group"
  style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/general/Resource_Groups.svg;dashed=1;fillColor=none;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="150" y="420" width="30" height="28" as="geometry" />
</mxCell>
```

### Logical Grouping Container (Gray Fill, No Stroke)

Use for grouping related services (e.g., "App Tier", "Data Tier", "Monitoring"):

```xml
<!-- Gray container for logical grouping -->
<mxCell id="app-tier" value=""
  style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#E6E6E6;strokeColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="200" y="100" width="300" height="200" as="geometry" />
</mxCell>
```

### Service Group (App Service Plan Pattern)

Group a service with its hosting plan using a parent group:

```xml
<!-- Group container (non-connectable) -->
<mxCell id="asp-group" connectable="0" value=""
  style="group;labelBackgroundColor=none;strokeColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="300" y="110" width="90" height="160" as="geometry" />
</mxCell>

<!-- White inner container with label -->
<mxCell id="asp-container" value="App Service Plan"
  style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#FFFFFF;labelPosition=center;verticalLabelPosition=top;align=center;verticalAlign=bottom;spacingTop=0;spacingBottom=-35;strokeColor=none;"
  vertex="1" parent="asp-group">
  <mxGeometry width="90" height="160" as="geometry" />
</mxCell>

<!-- Service icon inside the container -->
<mxCell id="web-app" value="Web App"
  style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/App_Services.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
  vertex="1" parent="asp-group">
  <mxGeometry x="13" y="80" width="64" height="64" as="geometry" />
</mxCell>
```

---

## Edge Patterns (Arrows)

### Data Flow (Solid Blue)

Primary data/request flow through the architecture:

```xml
<mxCell id="flow-data"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
  edge="1" parent="1" source="src" target="tgt">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Monitoring / Diagnostic Flow (Dashed)

Telemetry, logs, and metrics flowing to monitoring:

```xml
<mxCell id="flow-monitoring"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;labelBackgroundColor=none;"
  edge="1" parent="1" source="app" target="monitor">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Authentication / External Service Flow (Dashed)

Calls to identity providers, DNS, external services:

```xml
<mxCell id="flow-auth"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;labelBackgroundColor=none;"
  edge="1" parent="1" source="client" target="entra">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Cache / Return Flow (Solid Blue, Directional)

Data retrieval from cache or return paths:

```xml
<mxCell id="flow-cache"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=classic;endFill=0;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
  edge="1" parent="1" source="cache" target="app">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

Use a second edge in the opposite direction if you need an explicit return path.

---

## Azure Color Palette

Use these colors consistently for Azure architecture diagrams:

| Component Type | Fill Color | Stroke Color | CSS Hex | Use For |
|---------------|------------|--------------|---------|---------|
| **Compute** | `#E8F4FD` | `#0078D4` | Azure Blue | App Service, AKS, Container Apps, Functions, VMs |
| **Data** | `#E6F4EA` | `#107C10` | Green | Cosmos DB, SQL, Storage, Redis, PostgreSQL |
| **Integration** | `#F3E8FF` | `#8661C5` | Purple | Service Bus, Event Grid, Event Hubs, Logic Apps |
| **Network/Edge** | `#E0F7FA` | `#008272` | Teal | APIM, Front Door, App Gateway, Load Balancer, VNet |
| **Identity** | `#FFF4E5` | `#FF8C00` | Orange | Entra ID, Managed Identity, Key Vault |
| **AI/ML** | `#E3F2FD` | `#1976D2` | Deep Blue | Azure OpenAI, AI Foundry, Cognitive Services |
| **Monitoring** | `#FFF8E1` | `#FFC107` | Yellow | Azure Monitor, App Insights, Log Analytics |
| **Security** | `#FFEBEE` | `#D32F2F` | Red | WAF, Defender, Private Endpoints, NSG, Firewall |
| **External/Gray** | `#F5F5F5` | `#666666` | Gray | External systems, users, on-prem |

### Style Templates by Type

```xml
<!-- Compute (App Service, AKS, Container Apps, Functions) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E8F4FD;strokeColor=#0078D4;"

<!-- Data (Cosmos DB, SQL, Storage) - use cylinder for databases -->
style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E6F4EA;strokeColor=#107C10;"

<!-- Integration (Service Bus, Event Grid) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#F3E8FF;strokeColor=#8661C5;"

<!-- Network/Edge (APIM, Front Door, VNet boundary) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E0F7FA;strokeColor=#008272;"

<!-- Identity (Entra ID, Key Vault) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#FFF4E5;strokeColor=#FF8C00;"

<!-- AI/ML (Azure OpenAI, AI Foundry) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E3F2FD;strokeColor=#1976D2;"

<!-- Monitoring (Azure Monitor, App Insights) -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#FFF8E1;strokeColor=#FFC107;"

<!-- Security/Private Endpoint -->
style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#FFEBEE;strokeColor=#D32F2F;"

<!-- Trust Boundary (VNet, Subscription) - dashed container -->
style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=8 4;fillColor=none;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=14;fontStyle=1;"
```

---

## File Structure

### Root Element

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron" version="21.x.x">
  <diagram name="Page-1" id="unique-id">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <!-- Elements go here -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### mxGraphModel Attributes

| Attribute | Description | Recommended Value |
|-----------|-------------|-------------------|
| `dx` | Editor translation offset X (px, auto-managed) | 1200 |
| `dy` | Editor translation offset Y (px, auto-managed) | 800 |
| `grid` | Show grid | 1 |
| `gridSize` | Grid cell size | 10 |
| `guides` | Show guides | 1 |
| `tooltips` | Enable tooltips | 1 |
| `connect` | Enable connections | 1 |
| `arrows` | Enable arrows | 1 |
| `fold` | Enable folding | 1 |
| `page` | Page view enabled (1) or disabled (0) | 0 |
| `pageScale` | Page scale | 1 |
| `pageWidth` | Page width | 850 |
| `pageHeight` | Page height | 1100 |
| `math` | Enable math rendering | 0 |
| `shadow` | Enable shadows | 0 |
| `defaultFontFamily` | Default font | Segoe UI (for Azure) |

## Element Types

### Root Cells (Required)

```xml
<mxCell id="0" />
<mxCell id="1" parent="0" />
```

These two cells are ALWAYS required as the root of the diagram.

### Vertex (Box/Shape)

```xml
<mxCell id="box1"
  value="Label Text"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;"
  vertex="1"
  parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry" />
</mxCell>
```

### Edge (Arrow/Line)

> **⚠️ REQUIRED**: Edges should have either `source`/`target` terminals or explicit `sourcePoint`/`targetPoint` elements. If both are missing, the edge can render invisibly.

```xml
<mxCell id="arrow1"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;"
  edge="1"
  parent="1"
  source="box1"
  target="box2">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Edge with Explicit Points

Use when you need precise control or don't have vertex IDs to reference:

```xml
<mxCell id="arrow1"
  style="edgeStyle=none;curved=1;"
  edge="1"
  parent="1">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="200" y="150" as="sourcePoint" />
    <mxPoint x="400" y="150" as="targetPoint" />
    <Array as="points">
      <mxPoint x="300" y="100" />
    </Array>
  </mxGeometry>
</mxCell>
```

### Text Element

```xml
<mxCell id="label1"
  value="Standalone Text"
  style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=18;"
  vertex="1"
  parent="1">
  <mxGeometry x="100" y="50" width="200" height="30" as="geometry" />
</mxCell>
```

## Common Style Properties

### Shape Styles

| Property | Values | Description |
|----------|--------|-------------|
| `rounded` | 0, 1 | Rounded corners |
| `whiteSpace` | wrap, nowrap | Text wrapping |
| `html` | 0, 1 | HTML text support |
| `fillColor` | #RRGGBB, none | Background color |
| `strokeColor` | #RRGGBB, none | Border color |
| `strokeWidth` | number | Border width |
| `dashed` | 0, 1 | Dashed border |
| `opacity` | 0-100 | Transparency |
| `shadow` | 0, 1 | Drop shadow |

### Text Styles

| Property | Values | Description |
|----------|--------|-------------|
| `fontFamily` | font name | Font family (REQUIRED) |
| `fontSize` | number | Font size in px |
| `fontColor` | #RRGGBB | Text color |
| `fontStyle` | 0, 1, 2, 4 | 0=normal, 1=bold, 2=italic, 4=underline |
| `align` | left, center, right | Horizontal alignment |
| `verticalAlign` | top, middle, bottom | Vertical alignment |
| `labelPosition` | left, center, right | Label horizontal position |
| `verticalLabelPosition` | top, middle, bottom | Label vertical position |

### Edge Styles

| Property | Values | Description |
|----------|--------|-------------|
| `edgeStyle` | orthogonalEdgeStyle, entityRelationEdgeStyle, elbowEdgeStyle, none | Edge routing |
| `curved` | 0, 1 | Curved lines |
| `orthogonalLoop` | 0, 1 | Orthogonal loops |
| `jettySize` | auto, number | Connector size |
| `startArrow` | none, classic, block, diamond, oval | Start arrow style |
| `endArrow` | none, classic, block, diamond, oval | End arrow style |
| `startFill` | 0, 1 | Fill start arrow |
| `endFill` | 0, 1 | Fill end arrow |

### Connection Points

| Property | Values | Description |
|----------|--------|-------------|
| `exitX` | 0-1 | Exit point X (0=left, 1=right) |
| `exitY` | 0-1 | Exit point Y (0=top, 1=bottom) |
| `entryX` | 0-1 | Entry point X |
| `entryY` | 0-1 | Entry point Y |
| `exitDx` | number | Exit X offset |
| `exitDy` | number | Exit Y offset |
| `entryDx` | number | Entry X offset |
| `entryDy` | number | Entry Y offset |

## Predefined Shapes

### Basic Shapes

```xml
<!-- Rectangle -->
style="rounded=0;whiteSpace=wrap;html=1;"

<!-- Rounded Rectangle -->
style="rounded=1;whiteSpace=wrap;html=1;"

<!-- Ellipse -->
style="ellipse;whiteSpace=wrap;html=1;"

<!-- Diamond -->
style="rhombus;whiteSpace=wrap;html=1;"

<!-- Triangle -->
style="triangle;whiteSpace=wrap;html=1;"

<!-- Cylinder (Database) -->
style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;"

<!-- Cloud -->
style="ellipse;shape=cloud;whiteSpace=wrap;html=1;"
```

### Flowchart Shapes

```xml
<!-- Process -->
style="rounded=0;whiteSpace=wrap;html=1;"

<!-- Decision -->
style="rhombus;whiteSpace=wrap;html=1;"

<!-- Start/End -->
style="ellipse;whiteSpace=wrap;html=1;"

<!-- Document -->
style="shape=document;whiteSpace=wrap;html=1;"

<!-- Data -->
style="shape=parallelogram;whiteSpace=wrap;html=1;"
```

## Azure Architecture Shapes

Common patterns for Azure service representation:

### Compute Services

```xml
<!-- App Service / Container Apps / Functions (rounded rectangle) -->
<mxCell id="app" value="App Backend&#xa;(Container Apps)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E8F4FD;strokeColor=#0078D4;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="130" height="60" as="geometry" />
</mxCell>

<!-- AKS Cluster (with internal detail hint) -->
<mxCell id="aks" value="AKS Cluster&#xa;(3 nodes)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E8F4FD;strokeColor=#0078D4;strokeWidth=2;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="70" as="geometry" />
</mxCell>
```

### Data Services

```xml
<!-- Cosmos DB / SQL Database (cylinder) -->
<mxCell id="cosmos" value="Data Store&#xa;(Cosmos DB)"
  style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E6F4EA;strokeColor=#107C10;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="110" height="80" as="geometry" />
</mxCell>

<!-- Storage Account (rectangle with icon hint) -->
<mxCell id="storage" value="Blob Storage"
  style="rounded=0;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E6F4EA;strokeColor=#107C10;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="50" as="geometry" />
</mxCell>
```

### Network & Edge Services

```xml
<!-- API Management -->
<mxCell id="apim" value="API Gateway&#xa;(APIM)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E0F7FA;strokeColor=#008272;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry" />
</mxCell>

<!-- VNet Boundary (dashed container) -->
<mxCell id="vnet" value="Azure VNet (Private)"
  style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=8 4;fillColor=none;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=14;fontStyle=1;"
  vertex="1" parent="1">
  <mxGeometry x="50" y="50" width="500" height="300" as="geometry" />
</mxCell>

<!-- Private Endpoint -->
<mxCell id="pep" value="Private&#xa;Endpoint"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#FFEBEE;strokeColor=#D32F2F;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="90" height="50" as="geometry" />
</mxCell>
```

### AI & Integration Services

```xml
<!-- Azure OpenAI / AI Foundry -->
<mxCell id="openai" value="LLM Endpoint&#xa;(Azure OpenAI)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#E3F2FD;strokeColor=#1976D2;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="130" height="60" as="geometry" />
</mxCell>

<!-- Service Bus / Event Grid -->
<mxCell id="bus" value="Message Broker&#xa;(Service Bus)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#F3E8FF;strokeColor=#8661C5;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="130" height="60" as="geometry" />
</mxCell>
```

### Identity & Security

```xml
<!-- Entra ID -->
<mxCell id="entra" value="Entra ID"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#FFF4E5;strokeColor=#FF8C00;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="50" as="geometry" />
</mxCell>

<!-- Azure Firewall -->
<mxCell id="fw" value="Firewall&#xa;(Azure FW)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=14;fillColor=#FFEBEE;strokeColor=#D32F2F;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry" />
</mxCell>
```

### Monitoring

```xml
<!-- Azure Monitor / App Insights -->
<mxCell id="monitor" value="Monitoring&#xa;(App Insights)"
  style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#FFF8E1;strokeColor=#FFC107;"
  vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="50" as="geometry" />
</mxCell>
```

### Arrow Styles for Azure Diagrams

```xml
<!-- Primary data flow (solid, numbered) -->
<mxCell id="flow1"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;"
  edge="1" parent="1" source="src" target="tgt">
  <mxGeometry relative="1" as="geometry" />
</mxCell>

<!-- Monitoring/logging flow (dashed, yellow) -->
<mxCell id="mon-flow"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;dashed=1;strokeColor=#FFC107;"
  edge="1" parent="1" source="app" target="monitor">
  <mxGeometry relative="1" as="geometry" />
</mxCell>

<!-- Private Link connection (dashed, red) -->
<mxCell id="pep-flow"
  style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;dashed=1;strokeColor=#D32F2F;"
  edge="1" parent="1" source="pep" target="paas">
  <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Azure Service Icons (SVG)

You can embed built-in Azure service icons (diagrams.net) by adding an `image` vertex. The key is the `image=img/lib/azure2/.../*.svg` style.

Example (Azure AI Studio icon, commonly used for Azure AI Foundry / AI Studio visuals):

```xml
<mxCell id="foundry-icon" value=""
  style="image;aspect=fixed;html=1;align=center;fontSize=12;image=img/lib/azure2/ai_machine_learning/AI_Studio.svg;"
  vertex="1" parent="1">
  <mxGeometry x="242" y="382" width="36" height="36" as="geometry" />
</mxCell>
```

Notes:
- Icon paths look like: `img/lib/azure2/<category>/<icon>.svg`
- Keep icons small (24–40px) and place them inside/near the top-left of the relevant service box.
- Treat icons as overlays: keep the main box style consistent (color/border/labels).

## Font Recommendations

### Azure / Microsoft Style

| Font Name | Description |
|-----------|-------------|
| `Segoe UI` | **Preferred** for Azure diagrams (Microsoft brand font) |
| `Arial` | Cross-platform fallback |

### Japanese Fonts

| Font Name | Description |
|-----------|-------------|
| `Noto Sans JP` | Google's open source Japanese font |
| `Hiragino Kaku Gothic Pro` | macOS system font |
| `Yu Gothic` | Windows system font |
| `Meiryo` | Windows system font |

### System Fonts

| Font Name | Platform |
|-----------|----------|
| `Segoe UI` | Windows (preferred) |
| `Arial` | Cross-platform |
| `Helvetica` | macOS |

## Coordinate System

- Origin (0, 0) is at top-left
- X increases to the right
- Y increases downward
- All measurements are in pixels

```
(0,0) ───────────────────> X
  │
  │
  │
  │
  ▼
  Y
```

## Z-Order (Layering)

Elements are drawn in XML order:
1. First element = bottom layer (background)
2. Last element = top layer (foreground)

**Best Practice (Layering)**:
- Background containers first (tiers/boundaries, especially any filled rectangles)
- Edges next (connectors should not sit behind filled containers)
- Foreground vertices last (service icons/boxes and text labels)

This avoids a common failure mode where connectors appear “missing” because they are rendered underneath filled tier containers.

## mxGeometry Attributes

| Attribute | Type | Description |
|-----------|------|-------------|
| `x` | number | X position |
| `y` | number | Y position |
| `width` | number | Element width |
| `height` | number | Element height |
| `relative` | 0, 1 | Use relative positioning |
| `as` | "geometry" | Required identifier |

## Special Characters in Values

Use HTML entities for special characters:

| Character | Entity |
|-----------|--------|
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&` | `&amp;` |
| `"` | `&quot;` |
| `'` | `&apos;` |
| newline | `&#xa;` or `<br>` (with html=1) |
