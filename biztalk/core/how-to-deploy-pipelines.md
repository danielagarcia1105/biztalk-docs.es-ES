---
title: Cómo implementar canalizaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IReceiveLocation interface
- IReceivePort interface
- deploying, pipelines
- pipelines, deploying
- pipelines, compiling
- SendPipelineData method
- pipelines, configuring
- pipelines, code sample
- ReceivePipelineData property
- Validate method
- ISendPort interface
ms.assetid: 7a56c753-a0d4-48ed-a61d-e454bc9cd507
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23028db559864368bb091fb15abfca7e49d73808
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986325"
---
# <a name="how-to-deploy-pipelines"></a><span data-ttu-id="a9dd9-102">Cómo implementar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="a9dd9-102">How to Deploy Pipelines</span></span>
<span data-ttu-id="a9dd9-103">Las canalizaciones se compilan e implementan como parte del proceso de generación e implementación de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-103">Pipelines are compiled and deployed as part of the solution build and deploy process.</span></span> <span data-ttu-id="a9dd9-104">El compilador llama el **validar** método en cada componente, lo que permite a los componentes devolver errores de compilación de la información configurada.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-104">The compiler calls the **Validate** method on each component, allowing the components to return compile errors on the configured information.</span></span> <span data-ttu-id="a9dd9-105">Después de la generación, la canalización se implementa en el mismo ensamblado con el resto de la solución una vez que ésta se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-105">After building, the pipeline is deployed in the same assembly with the rest of the solution when the solution is deployed.</span></span>  
  
## <a name="per-instance-pipeline-configuration"></a><span data-ttu-id="a9dd9-106">Configuración de canalización por instancia</span><span class="sxs-lookup"><span data-stu-id="a9dd9-106">Per-instance pipeline configuration</span></span>  
 <span data-ttu-id="a9dd9-107">La configuración de canalización por instancia se utiliza para modificar las propiedades de componentes de canalización dentro de una canalización implementada en el nivel del puerto de envío o de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-107">Per-instance pipeline configuration is used to modify properties of pipeline components within a deployed pipeline at the send port or receive location level.</span></span> <span data-ttu-id="a9dd9-108">La configuración de canalización por instancia es útil cuando sólo se necesita modificar unas pocas propiedades de componentes de canalización por instancia.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-108">Per-instance pipeline configuration is useful when only a few pipeline component properties need to be modified per instance.</span></span> <span data-ttu-id="a9dd9-109">Por ejemplo, si necesita admitir diferentes tipos de mensajes en varias ubicaciones de recepción y tiene una única canalización de recepción XML personalizada, la configuración de la canalización por instancia le permite implementar la canalización y sobrescribir la configuración predeterminada (incluyendo determinar los diferentes sobres y nombres específicos del documento).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-109">For example, if you need to support different message types in multiple receive locations and have a single custom XML receive pipeline, per-instance pipeline configuration enables you to deploy the pipeline and override the default configuration (including specifying different envelope and document spec names).</span></span> <span data-ttu-id="a9dd9-110">Este mecanismo se admite en la consola de administración de BizTalk y a través del modelo de objetos del Explorador mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-110">This mechanism is supported in the BizTalk Management console and programmatically through the Explorer object model.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a><span data-ttu-id="a9dd9-111">Configuración de canalización por instancia mediante la Consola de administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a9dd9-111">Per-Instance Pipeline Configuration Using BizTalk Administration console</span></span>  
 <span data-ttu-id="a9dd9-112">Puede realizar la configuración de canalización por instancia mediante la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-112">You can perform per-instance pipeline configuration using the BizTalk Management console.</span></span> <span data-ttu-id="a9dd9-113">Una vez que haya implementado su canalización personalizada, cree todas las ubicaciones de recepción o puertos de envío que necesite.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-113">Once you have deployed your custom pipeline, create as many receive locations or send ports as required.</span></span> <span data-ttu-id="a9dd9-114">A continuación, sobrescriba los valores de propiedades predeterminados para cada puerto de envío o ubicación de recepción a través del cuadro de diálogo Configurar canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-114">Then for each receive location or send port, override default property values through the Configure Pipeline dialog box.</span></span> <span data-ttu-id="a9dd9-115">Por ejemplo, para especificar un esquema de documento diferente, escriba un nombre de esquema para el **EnvelopeDocSpecNames** propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-115">For example, to specify a different document schema, enter a schema name for the **EnvelopeDocSpecNames** property.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a9dd9-116">No se realizará ninguna validación de los valores de configuración especificados en la ubicación de recepción o puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-116">No validation of the configuration values specified in the receive location or send port will be performed.</span></span> <span data-ttu-id="a9dd9-117">Si la configuración es incorrecta, se producirá un error en los mensajes en tiempo de ejecución cuando pasen por la canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-117">If the configuration is incorrect, messages will fail at runtime when passing through the pipeline.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a><span data-ttu-id="a9dd9-118">Configuración de canalización por instancia mediante el modelo de objetos del Explorador</span><span class="sxs-lookup"><span data-stu-id="a9dd9-118">Per-Instance Pipeline Configuration Using the Explorer Object Model</span></span>  
 <span data-ttu-id="a9dd9-119">Cuando se lee el archivo XML que describe la configuración por instancia de los componentes de canalización, sobrescribe las propiedades establecidas en el archivo de canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-119">When the XML file describing the per-instance configuration of the pipeline components is read, it overrides the properties set in the pipeline file.</span></span>  
  
 <span data-ttu-id="a9dd9-120">La configuración de canalización por instancia se establece mediante el modelo de objetos del Explorador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-120">Per-instance pipeline configuration is set by using the BizTalk Explorer object model.</span></span> <span data-ttu-id="a9dd9-121">El modelo de objetos del explorador de BizTalk proporciona la **ReceivePipelineData** propiedad en el **IReceiveLocation** y **ISendPort** interfaces para establecer la configuración de componentes de canalización de recepción.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-121">The BizTalk Explorer object model provides the **ReceivePipelineData** property on the **IReceiveLocation** and **ISendPort** interfaces for setting the configuration of receive pipeline components.</span></span> <span data-ttu-id="a9dd9-122">El modelo de objetos del explorador de BizTalk también proporciona la **SendPipelineData** método en el **IReceivePort** y **ISendPort** interfaces para establecer la configuración de envío componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-122">The BizTalk Explorer object model also provides the **SendPipelineData** method on the **IReceivePort** and **ISendPort** interfaces for setting configuration of send pipeline components.</span></span>  
  
 <span data-ttu-id="a9dd9-123">La configuración de canalización por instancia no admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9dd9-123">Per-instance pipeline configuration does not support the following:</span></span>  
  
- <span data-ttu-id="a9dd9-124">Reorganizar fases dentro de la canalización</span><span class="sxs-lookup"><span data-stu-id="a9dd9-124">Rearranging stages within the pipeline</span></span>  
  
- <span data-ttu-id="a9dd9-125">Agregar o eliminar fases</span><span class="sxs-lookup"><span data-stu-id="a9dd9-125">Adding or removing stages</span></span>  
  
- <span data-ttu-id="a9dd9-126">Reorganizar componentes dentro de las fases</span><span class="sxs-lookup"><span data-stu-id="a9dd9-126">Rearranging components within stages</span></span>  
  
- <span data-ttu-id="a9dd9-127">Agregar o eliminar componentes</span><span class="sxs-lookup"><span data-stu-id="a9dd9-127">Adding or removing components</span></span>  
  
  <span data-ttu-id="a9dd9-128">Los únicos cambios admitidos son los de la configuración de los componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-128">The only supported changes are in the configuration of pipeline components.</span></span> <span data-ttu-id="a9dd9-129">La configuración por instancia de un componente de canalización sobrescribe la configuración habitual del componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-129">Per-instance configuration of a pipeline component overrides the common pipeline component configuration.</span></span> <span data-ttu-id="a9dd9-130">Si no se especifica un parámetro de un componente en la configuración de canalización por instancia, se utiliza la configuración habitual para ese parámetro (como se configuró en el Diseñador de canalizaciones).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-130">If a parameter of a component is not specified in per-instance pipeline configuration, the common configuration for that parameter (as configured in Pipeline Designer) is used.</span></span>  
  
  <span data-ttu-id="a9dd9-131">A continuación se muestra un ejemplo de datos de configuración por instancia.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-131">The following is an example of per-instance configuration data.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<Root xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
    <Stages>  
        <Stage CategoryId="9d0e4103-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft Microsoft.BizTalk.Component.MIME_SMIME_Decoder>  
                    <Properties>  
                        <AllowNonMIMEMessage vt=11>true</AllowNonMIMEMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e4105-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft.BizTalk.Component.XmlDasmComp>  
                    <Properties>  
                        <EnvelopeSpecNames vt=8>MySchemas.EnvelopeSpecNames</EnvelopeSpecNames>  
                        <AllowUnrecognizedMessage vt=11>false</AllowUnrecognizedMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e410d-4cce-4536-83fa-4a5040674ad6" ExecutionSequence="2">  
            <Components>  
                 <Component Name=Microsoft.BizTalk.Component.XmlValidator >  
                    <Properties>  
                        <DocumentSpecName vt=8>MySchemas.DocspecName</DocumentSpecName>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
    </Stages>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9dd9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9dd9-132">See Also</span></span>  
 [<span data-ttu-id="a9dd9-133">Desarrollo de componentes de canalización personalizados</span><span class="sxs-lookup"><span data-stu-id="a9dd9-133">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)