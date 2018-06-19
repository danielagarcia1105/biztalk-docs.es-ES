---
title: Cómo implementar canalizaciones | Documentos de Microsoft
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
ms.openlocfilehash: db6047752c45a2f72b615102e14a4e66839e3e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249604"
---
# <a name="how-to-deploy-pipelines"></a>Cómo implementar canalizaciones
Las canalizaciones se compilan e implementan como parte del proceso de generación e implementación de soluciones. El compilador llama el **validar** método en cada componente, lo que permite a los componentes devolver errores de compilación de la información configurada. Después de la generación, la canalización se implementa en el mismo ensamblado con el resto de la solución una vez que ésta se ha implementado.  
  
## <a name="per-instance-pipeline-configuration"></a>Configuración de canalización por instancia  
 La configuración de canalización por instancia se utiliza para modificar las propiedades de componentes de canalización dentro de una canalización implementada en el nivel del puerto de envío o de la ubicación de recepción. La configuración de canalización por instancia es útil cuando sólo se necesita modificar unas pocas propiedades de componentes de canalización por instancia. Por ejemplo, si necesita admitir diferentes tipos de mensajes en varias ubicaciones de recepción y tiene una única canalización de recepción XML personalizada, la configuración de la canalización por instancia le permite implementar la canalización y sobrescribir la configuración predeterminada (incluyendo determinar los diferentes sobres y nombres específicos del documento). Este mecanismo se admite en la consola de administración de BizTalk y a través del modelo de objetos del Explorador mediante programación.  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a>Configuración de canalización por instancia mediante la Consola de administración de BizTalk  
 Puede realizar la configuración de canalización por instancia mediante la consola de administración de BizTalk. Una vez que haya implementado su canalización personalizada, cree todas las ubicaciones de recepción o puertos de envío que necesite. A continuación, sobrescriba los valores de propiedades predeterminados para cada puerto de envío o ubicación de recepción a través del cuadro de diálogo Configurar canalización. Por ejemplo, para especificar un esquema de documento diferente, escriba un nombre de esquema para el **EnvelopeDocSpecNames** propiedad.  
  
> [!WARNING]
>  No se realizará ninguna validación de los valores de configuración especificados en la ubicación de recepción o puerto de envío. Si la configuración es incorrecta, se producirá un error en los mensajes en tiempo de ejecución cuando pasen por la canalización.  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a>Configuración de canalización por instancia mediante el modelo de objetos del Explorador  
 Cuando se lee el archivo XML que describe la configuración por instancia de los componentes de canalización, sobrescribe las propiedades establecidas en el archivo de canalización.  
  
 La configuración de canalización por instancia se establece mediante el modelo de objetos del Explorador de BizTalk. El modelo de objetos del explorador de BizTalk proporciona la **ReceivePipelineData** propiedad en el **IReceiveLocation** y **ISendPort** interfaces para establecer la configuración de componentes de canalización de recepción. El modelo de objetos del explorador de BizTalk también proporciona la **SendPipelineData** método en el **IReceivePort** y **ISendPort** interfaces para establecer la configuración de envío componentes de canalización.  
  
 La configuración de canalización por instancia no admite lo siguiente:  
  
-   Reorganizar fases dentro de la canalización  
  
-   Agregar o eliminar fases  
  
-   Reorganizar componentes dentro de las fases  
  
-   Agregar o eliminar componentes  
  
 Los únicos cambios admitidos son los de la configuración de los componentes de canalización. La configuración por instancia de un componente de canalización sobrescribe la configuración habitual del componente de canalización. Si no se especifica un parámetro de un componente en la configuración de canalización por instancia, se utiliza la configuración habitual para ese parámetro (como se configuró en el Diseñador de canalizaciones).  
  
 A continuación se muestra un ejemplo de datos de configuración por instancia.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Desarrollar componentes de canalización personalizado](../core/developing-custom-pipeline-components.md)