# draw.io Examples

## Azure Architecture Examples

These examples follow Azure best practices, WAF-aligned design, and the Azure color palette.

### Example A1: Azure AI App with Foundry (RAG Pattern)

A typical AI application using Azure AI Foundry with retrieval-augmented generation.

**WAF Pillars Shown**: Security (private endpoints, managed identity), Reliability (async pattern), Ops (monitoring)

**Key patterns demonstrated**:
- Azure icon library with correct paths
- **Separate text elements for arrow labels** (recommended over edge labels)
- Explicit sourcePoint/targetPoint for precise arrow positioning
- Trust boundary container

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Azure AI App" id="azure-ai-1">
    <mxGraphModel dx="1400" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- TRUST BOUNDARY: Azure VNet -->
        <mxCell id="vnet" value="Azure VNet (Private)" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=8 4;fillColor=none;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=14;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="220" y="40" width="610" height="370" as="geometry" />
        </mxCell>

        <!-- EDGES (no labels on edges - use separate text elements) -->
        
        <mxCell id="flow1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#FF8C00;labelBackgroundColor=none;"
          edge="1" parent="1" source="user" target="entra">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0078D4;labelBackgroundColor=none;"
          edge="1" parent="1" source="user" target="apim">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow3"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0078D4;labelBackgroundColor=none;"
          edge="1" parent="1" source="apim">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="400" y="196" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="flow4"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0078D4;labelBackgroundColor=none;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="468" y="196" as="sourcePoint" />
            <mxPoint x="560" y="196" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="flow5"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#107C10;labelBackgroundColor=none;"
          edge="1" parent="1" target="search">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="594" y="230" as="sourcePoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="flow6"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#1976D2;labelBackgroundColor=none;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="628" y="196" as="sourcePoint" />
            <mxPoint x="720" y="196" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="flow-mon"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;dashed=1;strokeColor=#FFC107;labelBackgroundColor=none;"
          edge="1" parent="1" target="monitor">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="434" y="230" as="sourcePoint" />
          </mxGeometry>
        </mxCell>

        <!-- ARROW LABELS (separate text elements - positioned above/beside arrows) -->
        <mxCell id="label1" value="1. Auth"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#FF8C00;"
          vertex="1" parent="1">
          <mxGeometry x="120" y="95" width="60" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label2" value="2. Request"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#0078D4;"
          vertex="1" parent="1">
          <mxGeometry x="140" y="170" width="70" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label3" value="3. Route"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#0078D4;"
          vertex="1" parent="1">
          <mxGeometry x="321" y="170" width="60" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label4" value="4. Orchestrate"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#0078D4;"
          vertex="1" parent="1">
          <mxGeometry x="480" y="170" width="80" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label5" value="5. Search"
          style="text;html=1;align=left;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#107C10;"
          vertex="1" parent="1">
          <mxGeometry x="605" y="260" width="60" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label6" value="6. Generate"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#1976D2;"
          vertex="1" parent="1">
          <mxGeometry x="640" y="170" width="70" height="20" as="geometry" />
        </mxCell>

        <mxCell id="label-mon" value="Logs"
          style="text;html=1;align=left;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;fontColor=#FFC107;"
          vertex="1" parent="1">
          <mxGeometry x="450" y="250" width="40" height="20" as="geometry" />
        </mxCell>

        <!-- ICONS (using Azure icon library) -->
        
        <mxCell id="user" value="Users"
          style="rounded=1;whiteSpace=wrap;html=1;fillColor=#F5F5F5;strokeColor=#666666;fontFamily=Segoe UI;fontSize=12;fontStyle=1;align=center;verticalAlign=middle;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="50" y="156" width="78" height="78" as="geometry" />
        </mxCell>

        <mxCell id="entra" value="Entra ID"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/identity/Azure_Active_Directory.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="56.5" y="30" width="67" height="70" as="geometry" />
        </mxCell>

        <mxCell id="apim" value="API Management"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/app_services/API_Management_Services.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="260" y="165" width="65" height="60" as="geometry" />
        </mxCell>

        <!-- NOTE: Container Apps uses Container_Instances.svg -->
        <mxCell id="app" value="Container Apps"
          style="image;aspect=fixed;html=1;points=[];align=center;fontSize=12;image=img/lib/azure2/compute/Container_Instances.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="400" y="157" width="64" height="68" as="geometry" />
        </mxCell>

        <!-- NOTE: AI Foundry uses AI_Studio.svg (not Machine_Learning.svg) -->
        <mxCell id="foundry" value="AI Foundry"
          style="image;aspect=fixed;html=1;points=[];align=center;fontSize=12;image=img/lib/azure2/ai_machine_learning/AI_Studio.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="566" y="157" width="64" height="68" as="geometry" />
        </mxCell>

        <mxCell id="search" value="AI Search"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/app_services/Search_Services.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="558" y="310" width="72" height="52" as="geometry" />
        </mxCell>

        <!-- Foundry models endpoint - also uses AI_Studio -->
        <mxCell id="openai" value="Foundry Models"
          style="image;aspect=fixed;html=1;points=[];align=center;fontSize=12;image=img/lib/azure2/ai_machine_learning/AI_Studio.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="720" y="160" width="64" height="68" as="geometry" />
        </mxCell>

        <mxCell id="monitor" value="App Insights"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/devops/Application_Insights.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="400" y="294" width="68" height="68" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### Example A2: Hub-Spoke with Private Endpoints

Enterprise landing zone pattern with hub VNet, spoke VNets, and private endpoints for PaaS services.

**WAF Pillars Shown**: Security (network isolation, private endpoints), Reliability (hybrid connectivity)

**Key patterns demonstrated**:
- Nested trust boundaries (subscription > VNet > subnet)
- Azure icons for Azure services only
- **Generic shapes for non-Azure entities** (On-Premises = gray box)
- Separate text elements for edge labels (positioned away from lines)
- Private endpoint dashed line pattern
- Components aligned horizontally to minimize edge bends

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Hub-Spoke" id="hub-spoke-1">
    <mxGraphModel dx="1400" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- TRUST BOUNDARIES -->
        <mxCell id="azure-sub" value="Azure Subscription" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=8 4;fillColor=none;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=14;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="40" width="650" height="400" as="geometry" />
        </mxCell>

        <mxCell id="hub-vnet" value="Hub VNet" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=4 4;fillColor=#E0F7FA;strokeColor=#008272;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=12;fontStyle=1;opacity=30;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="350" y="80" width="200" height="180" as="geometry" />
        </mxCell>

        <mxCell id="spoke-app" value="Spoke: App" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=4 4;fillColor=#E8F4FD;strokeColor=#0078D4;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=12;fontStyle=1;opacity=30;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="220" y="290" width="180" height="130" as="geometry" />
        </mxCell>

        <mxCell id="spoke-data" value="Spoke: Data" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=4 4;fillColor=#E6F4EA;strokeColor=#107C10;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=12;fontStyle=1;opacity=30;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="500" y="290" width="180" height="130" as="geometry" />
        </mxCell>

        <!-- EDGES FIRST (z-order: behind icons) -->
        <!-- NOTE: Components aligned at same y-coordinate (y=160) for straight horizontal arrow -->
        <mxCell id="vpn-conn"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#008272;labelBackgroundColor=none;"
          edge="1" parent="1" source="onprem" target="hub-fw">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <!-- Label as separate text element, positioned above the line -->
        <mxCell id="vpn-label" value="VPN/ExpressRoute"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="130" width="110" height="20" as="geometry" />
        </mxCell>

        <mxCell id="hub-spoke1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0078D4;labelBackgroundColor=none;"
          edge="1" parent="1" source="hub-fw" target="app-svc">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="hub-spoke2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#107C10;labelBackgroundColor=none;"
          edge="1" parent="1" source="hub-fw" target="pep-sql">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Private Endpoint to SQL - horizontal alignment for straight arrow -->
        <mxCell id="pep-conn"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;dashed=1;strokeColor=#D32F2F;labelBackgroundColor=none;"
          edge="1" parent="1" source="pep-sql" target="sql-db">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <!-- Private Link label positioned away from line -->
        <mxCell id="pep-label" value="Private Link"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;fontColor=#D32F2F;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="640" y="340" width="80" height="20" as="geometry" />
        </mxCell>

        <!-- COMPONENTS -->
        <!-- On-Premises: Use GENERIC gray box (not Azure icon!) -->
        <mxCell id="onprem" value="On-Premises"
          style="rounded=1;whiteSpace=wrap;html=1;fillColor=#E6E6E6;strokeColor=#666666;fontFamily=Segoe UI;fontSize=12;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="40" y="150" width="100" height="50" as="geometry" />
        </mxCell>

        <mxCell id="hub-fw" value="Azure Firewall"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/networking/Firewalls.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="405" y="120" width="71" height="56" as="geometry" />
        </mxCell>

        <mxCell id="hub-dns" value="Private DNS"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/networking/DNS_Zones.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="495" y="120" width="48" height="48" as="geometry" />
        </mxCell>

        <mxCell id="app-svc" value="App Service"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/App_Services.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="278" y="330" width="64" height="64" as="geometry" />
        </mxCell>

        <mxCell id="pep-sql" value="Private Endpoint"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=11;image=img/lib/azure2/networking/Private_Endpoint.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="555" y="355" width="52" height="52" as="geometry" />
        </mxCell>

        <!-- SQL Database: outside subscription boundary (PaaS accessed via Private Link) -->
        <mxCell id="sql-db" value="SQL Database"
          style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#E8F4FD;strokeColor=#0078D4;fontFamily=Segoe UI;fontSize=12;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="760" y="350" width="80" height="80" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### Example A3: Event-Driven Microservices

Async processing pattern with Service Bus, Container Apps, and full observability.

**WAF Pillars Shown**: Reliability (async decoupling), Performance (event-driven), Ops (full observability)

**Key patterns demonstrated**:
- Azure icons for Azure services, gray box for non-Azure "Event Source"
- Separate text labels (≥20px offset from arrows)
- Numbered flow sequence (1-5)
- Multiple monitoring connections (Service Bus, Functions, Container Apps → Monitor)
- Center alignment: Monitor x=402 aligns center with Functions (400+68/2=434, 402+64/2=434)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Event-Driven" id="event-driven-1">
    <mxGraphModel dx="1400" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- TRUST BOUNDARY -->
        <mxCell id="vnet" value="Azure VNet" 
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;dashPattern=8 4;fillColor=none;strokeColor=#0078D4;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontFamily=Segoe UI;fontSize=14;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="180" y="60" width="720" height="320" as="geometry" />
        </mxCell>

        <!-- EDGES FIRST (z-order: behind icons) -->
        <!-- NOTE: Edge labels are separate text elements positioned ≥20px from the line -->
        <mxCell id="flow1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;labelBackgroundColor=none;"
          edge="1" parent="1" source="source" target="bus">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#8661C5;labelBackgroundColor=none;"
          edge="1" parent="1" source="bus" target="processor">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow3"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0078D4;labelBackgroundColor=none;"
          edge="1" parent="1" source="processor" target="worker">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow4"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#107C10;labelBackgroundColor=none;"
          edge="1" parent="1" source="worker" target="cosmos">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow5"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;dashed=1;strokeColor=#8661C5;labelBackgroundColor=none;"
          edge="1" parent="1" source="worker" target="grid">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- MONITORING CONNECTIONS (yellow dashed) -->
        <!-- Service Bus → Monitor (enters left) -->
        <mxCell id="mon-bus"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;dashed=1;strokeColor=#FFC107;labelBackgroundColor=none;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;"
          edge="1" parent="1" source="bus" target="monitor">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Functions → Monitor (straight down - centers aligned) -->
        <mxCell id="mon-functions"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;dashed=1;strokeColor=#FFC107;labelBackgroundColor=none;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;"
          edge="1" parent="1" source="processor" target="monitor">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Container Apps → Monitor (enters right) -->
        <mxCell id="mon-container"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;dashed=1;strokeColor=#FFC107;labelBackgroundColor=none;exitX=0.25;exitY=1;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0;"
          edge="1" parent="1" source="worker" target="monitor">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- FLOW LABELS (separate text elements, ≥20px from lines) -->
        <mxCell id="flow1-label" value="1. Event"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="120" y="205" width="80" height="20" as="geometry" />
        </mxCell>

        <mxCell id="flow2-label" value="2. Subscribe"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;fontColor=#8661C5;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="300" y="205" width="90" height="20" as="geometry" />
        </mxCell>

        <mxCell id="flow3-label" value="3. Process"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;fontColor=#0078D4;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="490" y="205" width="80" height="20" as="geometry" />
        </mxCell>

        <mxCell id="flow4-label" value="4. Persist"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;fontColor=#107C10;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="660" y="205" width="80" height="20" as="geometry" />
        </mxCell>

        <mxCell id="flow5-label" value="5. Notify"
          style="text;html=1;align=left;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;fontColor=#8661C5;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="640" y="220" width="70" height="20" as="geometry" />
        </mxCell>

        <!-- COMPONENTS -->
        <!-- Event Source: Gray box (non-Azure external system) -->
        <mxCell id="source" value="Event Source"
          style="rounded=1;whiteSpace=wrap;html=1;fillColor=#E6E6E6;strokeColor=#666666;fontFamily=Segoe UI;fontSize=12;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="0" y="152" width="100" height="50" as="geometry" />
        </mxCell>

        <mxCell id="bus" value="Service Bus"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/integration/Service_Bus.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="210" y="145" width="65" height="63" as="geometry" />
        </mxCell>

        <mxCell id="processor" value="Functions"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/Function_Apps.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="400" y="147" width="68" height="60" as="geometry" />
        </mxCell>

        <!-- NOTE: Container Apps uses Container_Instances.svg -->
        <mxCell id="worker" value="Container Apps"
          style="image;aspect=fixed;html=1;points=[];align=center;fontSize=12;image=img/lib/azure2/compute/Container_Instances.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="576" y="143" width="64" height="68" as="geometry" />
        </mxCell>

        <mxCell id="cosmos" value="Cosmos DB"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/databases/Azure_Cosmos_DB.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="770" y="145" width="64" height="64" as="geometry" />
        </mxCell>

        <mxCell id="grid" value="Event Grid"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/integration/Event_Grid_Topics.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="583" y="280" width="52" height="52" as="geometry" />
        </mxCell>

        <!-- Monitor: x=402 aligns center (434) with Functions center (434) for straight vertical line -->
        <mxCell id="monitor" value="Azure Monitor"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/management_governance/Monitor.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;fontFamily=Segoe UI;"
          vertex="1" parent="1">
          <mxGeometry x="402" y="268" width="64" height="64" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## Example A5: Comparison Diagram (Current vs Target)

Side-by-side architecture comparison with proper annotations, spacing, and color coding.

**Pattern**: Current state (problems) vs Target state (benefits)
**Use for**: Executive presentations, architecture decision records, migration proposals

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Current vs Target" id="comparison-1">
    <mxGraphModel dx="1400" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- TITLE -->
        <mxCell id="title" value="AI Platform: Current vs Target Architecture"
          style="text;html=1;align=center;fontFamily=Segoe UI;fontSize=20;fontStyle=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="10" width="500" height="30" as="geometry" />
        </mxCell>

        <!-- SUBTITLE -->
        <mxCell id="subtitle" value="Audience: D&amp;A Leadership | Jan 28, 2026"
          style="text;html=1;align=center;fontFamily=Segoe UI;fontSize=12;fontColor=#666666;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="38" width="500" height="20" as="geometry" />
        </mxCell>

        <!-- CURRENT STATE CONTAINER (Orange/Red) -->
        <mxCell id="current-state" value="Current State"
          style="rounded=0;whiteSpace=wrap;html=1;fillColor=#FFF3E0;strokeColor=#E65100;strokeWidth=2;verticalAlign=top;fontFamily=Segoe UI;fontSize=16;fontStyle=1;spacingTop=5;align=left;spacingLeft=10;"
          vertex="1" parent="1">
          <mxGeometry x="40" y="70" width="280" height="320" as="geometry" />
        </mxCell>

        <!-- TARGET STATE CONTAINER (Green) -->
        <mxCell id="target-state" value="Target State"
          style="rounded=0;whiteSpace=wrap;html=1;fillColor=#E8F5E9;strokeColor=#2E7D32;strokeWidth=2;verticalAlign=top;fontFamily=Segoe UI;fontSize=16;fontStyle=1;spacingTop=5;align=left;spacingLeft=10;"
          vertex="1" parent="1">
          <mxGeometry x="360" y="70" width="280" height="320" as="geometry" />
        </mxCell>

        <!-- ARROWS (behind components) -->
        <mxCell id="flow-current1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#E65100;labelBackgroundColor=none;"
          edge="1" parent="1" source="current-docs" target="current-lib">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow-current2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#E65100;labelBackgroundColor=none;"
          edge="1" parent="1" source="current-lib" target="current-db">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow-target1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#2E7D32;labelBackgroundColor=none;"
          edge="1" parent="1" source="target-docs" target="target-docintel">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow-target2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#2E7D32;labelBackgroundColor=none;"
          edge="1" parent="1" source="target-docintel" target="target-search">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- CURRENT STATE COMPONENTS -->
        <mxCell id="current-docs" value="PDF Documents"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/general/File.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="130" y="110" width="50" height="50" as="geometry" />
        </mxCell>

        <mxCell id="current-lib" value="Python Library"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#FFEBEE;strokeColor=#D32F2F;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="200" width="110" height="40" as="geometry" />
        </mxCell>

        <!-- Warning annotation (anchored near component) -->
        <mxCell id="warning1" value="⚠ No OCR&#xa;⚠ Images skipped"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=10;fillColor=#FFEBEE;strokeColor=#D32F2F;fontColor=#C62828;align=left;spacingLeft=5;"
          vertex="1" parent="1">
          <mxGeometry x="220" y="200" width="90" height="40" as="geometry" />
        </mxCell>

        <mxCell id="current-db" value="Vector DB&#xa;(Semantic Only)"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#FFEBEE;strokeColor=#D32F2F;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="290" width="110" height="50" as="geometry" />
        </mxCell>

        <mxCell id="warning2" value="⚠ No hybrid search&#xa;⚠ No reranking"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=10;fillColor=#FFEBEE;strokeColor=#D32F2F;fontColor=#C62828;align=left;spacingLeft=5;"
          vertex="1" parent="1">
          <mxGeometry x="220" y="290" width="90" height="40" as="geometry" />
        </mxCell>

        <!-- TARGET STATE COMPONENTS -->
        <mxCell id="target-docs" value="PDF Documents"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/general/File.svg;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="390" y="110" width="50" height="50" as="geometry" />
        </mxCell>

        <mxCell id="target-docintel" value="Document Intelligence"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#E3F2FD;strokeColor=#1976D2;"
          vertex="1" parent="1">
          <mxGeometry x="375" y="200" width="130" height="40" as="geometry" />
        </mxCell>

        <!-- Benefit annotation (anchored near component) -->
        <mxCell id="benefit1" value="✓ Full OCR + images&#xa;✓ Table extraction"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=10;fillColor=#E8F5E9;strokeColor=#2E7D32;fontColor=#1B5E20;align=left;spacingLeft=5;"
          vertex="1" parent="1">
          <mxGeometry x="515" y="200" width="110" height="40" as="geometry" />
        </mxCell>

        <mxCell id="target-search" value="AI Search&#xa;(Hybrid + Rerank)"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fillColor=#E6F4EA;strokeColor=#107C10;"
          vertex="1" parent="1">
          <mxGeometry x="375" y="290" width="130" height="50" as="geometry" />
        </mxCell>

        <mxCell id="benefit2" value="✓ Hybrid search&#xa;✓ Semantic reranking&#xa;✓ Metadata filtering"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=10;fillColor=#E8F5E9;strokeColor=#2E7D32;fontColor=#1B5E20;align=left;spacingLeft=5;"
          vertex="1" parent="1">
          <mxGeometry x="515" y="285" width="115" height="55" as="geometry" />
        </mxCell>

        <!-- KEY PRINCIPLE (bottom) -->
        <mxCell id="principle" value="Key Principle: Use the right tool for the job"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Segoe UI;fontSize=12;fontStyle=1;fillColor=#E3F2FD;strokeColor=#1976D2;fontColor=#0D47A1;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="410" width="280" height="30" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

**Key patterns in this example:**
- Title and subtitle are separate text elements
- Current state uses orange border (`#E65100`) with light orange fill (`#FFF3E0`)
- Target state uses green border (`#2E7D32`) with light green fill (`#E8F5E9`)
- Warning annotations in red boxes, anchored near the problem component
- Benefit annotations in green boxes, anchored near the improved component
- Components sized to fit text (width > longest line × 8px + 20px)
- Consistent vertical alignment between left and right sides

---

## Generic Examples (Flowcharts, Sequences)

These examples demonstrate core XML mechanics with proper font settings and arrow placement.

---

## Example A4: Web App with Azure Icons (Enterprise Pattern)

Production-quality diagram using Azure icon library, container grouping, and proper edge patterns.

**Pattern**: Web app → Queue → Functions → Database, with monitoring, auth, and CDN
**WAF Pillars**: Security (Entra auth, WAF), Performance (CDN, Redis), Ops (full monitoring)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Web App Enterprise" id="web-app-enterprise">
    <mxGraphModel dx="1400" dy="900" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Segoe UI">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- RESOURCE GROUP BOUNDARY -->
        <mxCell id="rg-boundary" value=""
          style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;dashed=1;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="160" y="40" width="900" height="380" as="geometry" />
        </mxCell>

        <!-- LOGICAL TIER CONTAINERS (gray fill, no stroke) -->
        <!-- App Tier -->
        <mxCell id="app-tier" value=""
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#E6E6E6;strokeColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="280" y="100" width="340" height="200" as="geometry" />
        </mxCell>

        <!-- Data Tier -->
        <mxCell id="data-tier" value=""
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#E6E6E6;strokeColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="720" y="60" width="280" height="160" as="geometry" />
        </mxCell>

        <!-- Monitoring Tier -->
        <mxCell id="mon-tier" value=""
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#E6E6E6;strokeColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="720" y="240" width="280" height="160" as="geometry" />
        </mxCell>

        <!-- EDGES FIRST (z-order: behind shapes) -->
        <!-- Auth flow (dashed) -->
        <mxCell id="flow-auth"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;labelBackgroundColor=none;"
          edge="1" parent="1" source="internet" target="entra">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Data flows (solid blue) -->
        <mxCell id="flow1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="internet" target="front-door">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="front-door" target="web-app">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow3"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="web-app" target="queue">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow4"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="queue" target="function">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow5"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="function" target="sql">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Cache flow (directional; add reverse edge if needed) -->
        <mxCell id="flow-cache"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;endArrow=classic;endFill=0;fillColor=#dae8fc;strokeColor=#6c8ebf;labelBackgroundColor=none;"
          edge="1" parent="1" source="web-app" target="redis">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- Monitoring flows (dashed) -->
        <mxCell id="flow-mon1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;labelBackgroundColor=none;"
          edge="1" parent="1" source="web-app" target="monitor">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="flow-mon2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;dashed=1;labelBackgroundColor=none;"
          edge="1" parent="1" source="function" target="log-analytics">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- EDGE LABELS (separate text elements, ≥20px from lines) -->
        <mxCell id="flow-auth-label" value="Authentication"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="10" y="120" width="90" height="20" as="geometry" />
        </mxCell>

        <mxCell id="flow-mon1-label" value="Metrics &amp; Logs"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Segoe UI;fontSize=11;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="660" y="240" width="90" height="20" as="geometry" />
        </mxCell>

        <!-- EXTERNAL SERVICES (outside boundary) -->
        <mxCell id="entra" value="Entra ID"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/identity/Azure_Active_Directory.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="50" y="20" width="62" height="70" as="geometry" />
        </mxCell>

        <mxCell id="internet" value="Internet"
          style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#F5F5F5;strokeColor=#666666;fontFamily=Segoe UI;fontSize=12;fontStyle=1;align=center;verticalAlign=middle;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="50" y="170" width="65" height="65" as="geometry" />
        </mxCell>

        <!-- EDGE / CDN -->
        <mxCell id="front-door" value="Azure Front Door&#xa;WAF + CDN"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/networking/Front_Doors.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="180" y="174" width="68" height="60" as="geometry" />
        </mxCell>

        <!-- APP SERVICE PLAN GROUP -->
        <mxCell id="asp-group" connectable="0" value=""
          style="group;labelBackgroundColor=none;strokeColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="295" y="115" width="90" height="160" as="geometry" />
        </mxCell>

        <mxCell id="asp-container" value="App Service Plan"
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#FFFFFF;labelPosition=center;verticalLabelPosition=top;align=center;verticalAlign=bottom;spacingTop=0;spacingBottom=-35;strokeColor=none;"
          vertex="1" parent="asp-group">
          <mxGeometry width="90" height="160" as="geometry" />
        </mxCell>

        <mxCell id="web-app" value="Web App"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/App_Services.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
          vertex="1" parent="asp-group">
          <mxGeometry x="13" y="80" width="64" height="64" as="geometry" />
        </mxCell>

        <!-- QUEUE -->
        <mxCell id="queue" value="Queue"
          style="verticalLabelPosition=top;html=1;verticalAlign=bottom;align=center;strokeColor=none;fillColor=#00BEF2;shape=mxgraph.azure.storage_queue;labelPosition=center;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="430" y="180" width="50" height="45" as="geometry" />
        </mxCell>

        <!-- FUNCTION APP GROUP -->
        <mxCell id="func-group" connectable="0" value=""
          style="group;labelBackgroundColor=none;strokeColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="515" y="115" width="90" height="160" as="geometry" />
        </mxCell>

        <mxCell id="func-container" value=""
          style="rounded=0;whiteSpace=wrap;html=1;dashed=1;labelBackgroundColor=none;fillColor=#FFFFFF;labelPosition=center;verticalLabelPosition=top;align=center;verticalAlign=bottom;spacingTop=0;spacingBottom=-35;strokeColor=none;"
          vertex="1" parent="func-group">
          <mxGeometry width="90" height="160" as="geometry" />
        </mxCell>

        <mxCell id="function" value="Function App"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/compute/Function_Apps.svg;labelPosition=center;verticalLabelPosition=top;verticalAlign=bottom;labelBackgroundColor=none;"
          vertex="1" parent="func-group">
          <mxGeometry x="11" y="83" width="68" height="60" as="geometry" />
        </mxCell>

        <!-- DATA SERVICES -->
        <mxCell id="sql" value="Azure SQL Database"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/databases/SQL_Database.svg;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="760" y="80" width="48" height="64" as="geometry" />
        </mxCell>

        <mxCell id="cosmos" value="Cosmos DB"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/databases/Azure_Cosmos_DB.svg;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="880" y="80" width="64" height="64" as="geometry" />
        </mxCell>

        <mxCell id="redis" value="Redis Cache"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/databases/Cache_Redis.svg;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="640" y="160" width="64" height="52" as="geometry" />
        </mxCell>

        <!-- MONITORING SERVICES -->
        <mxCell id="monitor" value="Azure Monitor"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/management_governance/Monitor.svg;dashed=1;labelBackgroundColor=none;fillColor=#FFFFFF;"
          vertex="1" parent="1">
          <mxGeometry x="760" y="270" width="64" height="64" as="geometry" />
        </mxCell>

        <mxCell id="log-analytics" value="Log Analytics"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/analytics/Log_Analytics_Workspaces.svg;dashed=1;labelBackgroundColor=none;fillColor=#FFFFFF;"
          vertex="1" parent="1">
          <mxGeometry x="880" y="270" width="64" height="64" as="geometry" />
        </mxCell>

        <!-- RESOURCE GROUP LABEL -->
        <mxCell id="rg-label" value="Resource Group"
          style="aspect=fixed;html=1;points=[];align=center;image;fontSize=12;image=img/lib/azure2/general/Resource_Groups.svg;dashed=1;fillColor=none;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="150" y="400" width="30" height="28" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Simple Flow" id="simple-flow-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Noto Sans JP">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- ARROWS FIRST (renders at back) -->
        <mxCell id="arrow1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;"
          edge="1" parent="1" source="step1" target="step2">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="arrow2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;"
          edge="1" parent="1" source="step2" target="step3">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- BOXES AFTER (renders in front) -->
        <mxCell id="step1" value="開始"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#dae8fc;strokeColor=#6c8ebf;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="100" width="120" height="60" as="geometry" />
        </mxCell>

        <mxCell id="step2" value="処理"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#d5e8d4;strokeColor=#82b366;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="220" width="120" height="60" as="geometry" />
        </mxCell>

        <mxCell id="step3" value="終了"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#f8cecc;strokeColor=#b85450;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="340" width="120" height="60" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Example 2: Architecture Diagram with Labels

A system architecture diagram with labeled arrows.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Architecture" id="arch-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Noto Sans JP">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- ARROWS FIRST -->
        <mxCell id="conn1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;"
          edge="1" parent="1" source="client" target="api">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="conn2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;"
          edge="1" parent="1" source="api" target="db">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- LABELS (positioned above arrows) -->
        <mxCell id="label1" value="REST API"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;fontStyle=0;"
          vertex="1" parent="1">
          <mxGeometry x="250" y="90" width="100" height="30" as="geometry" />
        </mxCell>

        <mxCell id="label2" value="SQL Query"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;fontStyle=0;"
          vertex="1" parent="1">
          <mxGeometry x="500" y="90" width="100" height="30" as="geometry" />
        </mxCell>

        <!-- BOXES -->
        <mxCell id="client" value="クライアント&#xa;(Browser)"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#fff2cc;strokeColor=#d6b656;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="100" width="140" height="80" as="geometry" />
        </mxCell>

        <mxCell id="api" value="APIサーバー&#xa;(Node.js)"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#dae8fc;strokeColor=#6c8ebf;"
          vertex="1" parent="1">
          <mxGeometry x="340" y="100" width="140" height="80" as="geometry" />
        </mxCell>

        <mxCell id="db" value="データベース&#xa;(PostgreSQL)"
          style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#d5e8d4;strokeColor=#82b366;"
          vertex="1" parent="1">
          <mxGeometry x="580" y="90" width="140" height="100" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Example 3: Decision Flowchart

A flowchart with conditional branching.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Decision Flow" id="decision-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Noto Sans JP">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- ARROWS -->
        <mxCell id="a1"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;"
          edge="1" parent="1" source="start" target="check">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="a2"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;exitX=1;exitY=0.5;exitDx=0;exitDy=0;"
          edge="1" parent="1" source="check" target="success">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="a3"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;exitX=0;exitY=0.5;exitDx=0;exitDy=0;"
          edge="1" parent="1" source="check" target="retry">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <mxCell id="a4"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;"
          edge="1" parent="1" source="retry" target="check">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="80" y="320" />
              <mxPoint x="80" y="200" />
            </Array>
          </mxGeometry>
        </mxCell>

        <!-- EDGE LABELS (separate text elements, ≥20px from lines) -->
        <mxCell id="a2-label" value="Yes"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="330" y="175" width="40" height="20" as="geometry" />
        </mxCell>

        <mxCell id="a3-label" value="No"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;labelBackgroundColor=none;"
          vertex="1" parent="1">
          <mxGeometry x="110" y="240" width="40" height="20" as="geometry" />
        </mxCell>

        <!-- SHAPES -->
        <mxCell id="start" value="開始"
          style="ellipse;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#d5e8d4;strokeColor=#82b366;"
          vertex="1" parent="1">
          <mxGeometry x="200" y="50" width="100" height="60" as="geometry" />
        </mxCell>

        <mxCell id="check" value="条件を&#xa;満たすか？"
          style="rhombus;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=16;fillColor=#fff2cc;strokeColor=#d6b656;"
          vertex="1" parent="1">
          <mxGeometry x="175" y="160" width="150" height="80" as="geometry" />
        </mxCell>

        <mxCell id="success" value="成功"
          style="ellipse;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#dae8fc;strokeColor=#6c8ebf;"
          vertex="1" parent="1">
          <mxGeometry x="400" y="170" width="100" height="60" as="geometry" />
        </mxCell>

        <mxCell id="retry" value="再試行"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#f8cecc;strokeColor=#b85450;"
          vertex="1" parent="1">
          <mxGeometry x="125" y="290" width="100" height="60" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Example 4: Sequence-Style Diagram

Horizontal flow with multiple participants.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Sequence Style" id="seq-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Noto Sans JP">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- ARROWS (horizontal with labels above) -->
        <mxCell id="msg1"
          style="edgeStyle=none;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;endArrow=classic;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="170" y="200" as="sourcePoint" />
            <mxPoint x="330" y="200" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="msg1_label" value="リクエスト送信"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;"
          vertex="1" parent="1">
          <mxGeometry x="190" y="165" width="120" height="30" as="geometry" />
        </mxCell>

        <mxCell id="msg2"
          style="edgeStyle=none;html=1;strokeWidth=2;fontFamily=Noto Sans JP;fontSize=14;endArrow=classic;dashed=1;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="330" y="260" as="sourcePoint" />
            <mxPoint x="170" y="260" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="msg2_label" value="レスポンス返却"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;"
          vertex="1" parent="1">
          <mxGeometry x="190" y="265" width="120" height="30" as="geometry" />
        </mxCell>

        <!-- PARTICIPANTS -->
        <mxCell id="user" value="ユーザー"
          style="rounded=0;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#dae8fc;strokeColor=#6c8ebf;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="80" width="140" height="60" as="geometry" />
        </mxCell>

        <mxCell id="server" value="サーバー"
          style="rounded=0;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#d5e8d4;strokeColor=#82b366;"
          vertex="1" parent="1">
          <mxGeometry x="260" y="80" width="140" height="60" as="geometry" />
        </mxCell>

        <!-- LIFELINES -->
        <mxCell id="line1"
          style="edgeStyle=none;html=1;strokeWidth=1;dashed=1;strokeColor=#999999;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="170" y="140" as="sourcePoint" />
            <mxPoint x="170" y="320" as="targetPoint" />
          </mxGeometry>
        </mxCell>

        <mxCell id="line2"
          style="edgeStyle=none;html=1;strokeWidth=1;dashed=1;strokeColor=#999999;"
          edge="1" parent="1">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="330" y="140" as="sourcePoint" />
            <mxPoint x="330" y="320" as="targetPoint" />
          </mxGeometry>
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Example 5: Diagram with Title and Description

Complete diagram with header text.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron">
  <diagram name="Titled Diagram" id="titled-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="0" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" defaultFontFamily="Noto Sans JP">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />

        <!-- TITLE (sufficient width for Japanese) -->
        <mxCell id="title" value="システム構成図"
          style="text;html=1;align=center;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=24;fontStyle=1;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="30" width="280" height="40" as="geometry" />
        </mxCell>

        <!-- DESCRIPTION -->
        <mxCell id="desc" value="本番環境のシステム構成を示す図です"
          style="text;html=1;align=left;verticalAlign=middle;fontFamily=Noto Sans JP;fontSize=14;fontColor=#666666;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="70" width="400" height="30" as="geometry" />
        </mxCell>

        <!-- ARROW -->
        <mxCell id="conn"
          style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;"
          edge="1" parent="1" source="box1" target="box2">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>

        <!-- CONTENT -->
        <mxCell id="box1" value="Webサーバー"
          style="rounded=1;whiteSpace=wrap;html=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#dae8fc;strokeColor=#6c8ebf;"
          vertex="1" parent="1">
          <mxGeometry x="100" y="130" width="150" height="70" as="geometry" />
        </mxCell>

        <mxCell id="box2" value="データベース"
          style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;fontFamily=Noto Sans JP;fontSize=18;fillColor=#d5e8d4;strokeColor=#82b366;"
          vertex="1" parent="1">
          <mxGeometry x="320" y="120" width="120" height="90" as="geometry" />
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

## Usage Notes

1. **Copy and Modify**: Use these examples as templates
2. **Unique IDs**: Always use unique `id` attributes for each element
3. **Font Consistency**: Ensure `fontFamily` is set on ALL text elements
4. **PNG Verification**: Always export to PNG and verify visually

## Common Modifications

### Change Colors

Replace fill and stroke colors:
- Blue: `fillColor=#dae8fc;strokeColor=#6c8ebf;`
- Green: `fillColor=#d5e8d4;strokeColor=#82b366;`
- Yellow: `fillColor=#fff2cc;strokeColor=#d6b656;`
- Red: `fillColor=#f8cecc;strokeColor=#b85450;`
- Purple: `fillColor=#e1d5e7;strokeColor=#9673a6;`
- Gray: `fillColor=#f5f5f5;strokeColor=#666666;`

### Adjust Font Size

```xml
<!-- Small (not recommended) -->
fontSize=12

<!-- Normal -->
fontSize=14

<!-- Recommended -->
fontSize=18

<!-- Large (titles) -->
fontSize=24
```

### Add Rounded Corners

```xml
<!-- Square corners -->
rounded=0

<!-- Rounded corners -->
rounded=1
```
