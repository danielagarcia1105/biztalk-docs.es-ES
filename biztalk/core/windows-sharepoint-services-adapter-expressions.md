---
title: Expresiones del adaptador de Windows SharePoint Services | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- macros, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], supported macros
- configuring [Windows SharePoint Services adapters], expressions
- Windows SharePoint Services adapters, expressions
ms.assetid: 15e3afb2-0ef8-41b4-b3ec-de84af738c12
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf777931837f036f7228c4a359eef77faa9e97e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter-expressions"></a>Expresiones del adaptador de Windows SharePoint Services
Este tema describe el formato y el significado de las cadenas que se pueden especificar como valores para la **archivo NameProperty origen** propiedades del adaptador de Windows SharePoint Services. También se describen las propiedades de contexto relacionadas, **WSS. Nombre de archivo** y **WSS. ConfigPropertiesXml**. Estas expresiones permiten definir con facilidad el valor del nombre de archivo o el valor de columna de Windows SharePoint Services personalizado, basado en literales y valores extraídos del mensaje o del sistema de BizTalk.  
  
 Las expresiones pueden contener literales y macros. Los literales se mostrarán en el nombre de archivo exactamente como se escribieron. Las macros deben colocarse entre caracteres '%'. Un ejemplo de macro es `%MessageID%` que, en tiempo de ejecución, se reemplazará con el GUID del mensaje.  
  
> [!NOTE]
>  Cuando el carácter % se utiliza como un literal o dentro de una expresión XPATH, deben convertirse así \\%. Un solo carácter % se considerará un delimitador de macro, donde un \\% se reemplazará en tiempo de ejecución por un solo carácter %. El \ caracteres deben convertirse así \\ \\.  
  
## <a name="expression-examples"></a>Ejemplos de expresiones  
  
|Valor en tiempo de diseño|Valor en tiempo de ejecución|  
|-----------------------|-------------------|  
|XYZ|XYZ|  
|PurchaseOrder|PurchaseOrder|  
|%MessageID%|55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|PurchaseOrder - %MessageID%|PurchaseOrder - 55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|Descuento \\% 10|Descuento %10|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – 10001|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:PartnerName%-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – Contoso-10001|  
  
## <a name="supported-macros"></a>Macros admitidas  
  
|Valor en tiempo de diseño|Valor en tiempo de ejecución|  
|-----------------------|-------------------|  
|%MessageID%|Identificador del mensaje de BizTalk que constituye un GUID único.|  
|%SendingOrchestrationID%|Identificador de BizTalk de la instancia de orquestación en la que se originó el mensaje.|  
|%SendingOrchestrationType%|Nombre de tipo de la orquestación en la que se originó el mensaje.|  
|% XPATH =\<xpath > %|Permite especificar un elemento XPATH para que se utilice para extraer el valor del mensaje. "\<xpath >" debe sustituirse por una expresión XPATH válida. **Nota:** el alias de espacio de nombres debe definirse fuera de la expresión en el 'Alias Namespace' o WSS. Campo ConfigNamespaceAliases.|  
|%Filename%|Se reemplaza con el valor de nombre de archivo extraído de la propiedad de contexto del mensaje WSS.Filename. Los mensajes recibidos de SharePoint tienen el valor de la propiedad de contexto de mensaje WSS.Filename establecida en el nombre del archivo SharePoint. El valor devuelto se preprocesa utilizando Path.GetFilenameWithoutExtension. **Nota:** no se puede usar esta macro en WSS. Propiedades de contexto de configuración * (desde la orquestación).|  
|%Extension%|Se reemplaza con el valor de la extensión de archivo extraído de la propiedad de contexto del mensaje WSS.Filename. Los mensajes recibidos de SharePoint tienen el valor de la propiedad de contexto de mensaje WSS.Filename establecida en el nombre del archivo SharePoint. El valor devuelto se preprocesa utilizando Path.GetExtension. El valor devuelto no contendrá ".". **Nota:** no se puede usar esta macro en WSS. Propiedades de contexto de configuración * (desde la orquestación).|  
  
 Toda expresión válida que admita la promoción de propiedades es un nombre de archivo de tiempo de diseño válido. El nombre de archivo de tiempo de diseño se ampliará en tiempo de ejecución a los nombres de archivo de Windows SharePoint Services. Este nombre de archivo de Windows SharePoint Services tiene algunas limitaciones adicionales que se describen del modo siguiente:  
  
-   Los nombres de archivo de Windows válidos pueden contener caracteres Unicode, con las siguientes excepciones: /  \  :  *  ?  \<> &#124;  "# {} % & ~ o caracteres de tabulación y varios puntos.  
  
-   El nombre de archivo no puede tener más de 256 caracteres y la longitud total de la dirección URL debe ser, a lo sumo, de 256 caracteres.  
  
-   Si el nombre de archivo de Windows SharePoint Services expandido contiene caracteres no válidos, o si la dirección URL o el nombre de archivo expandido es demasiado largo, se registrará un error en el registro de eventos de la aplicación y el mensaje se suspenderá. El estado de mensaje y el error también estarán visibles en la página Concentrador de grupo mediante el seguimiento de instancias de servicios y eventos de mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar Windows SharePoint Services ubicación de recepción](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Cómo configurar un controlador de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Admite los tipos de columna de Windows SharePoint Services](../core/supported-windows-sharepoint-services-column-types.md)