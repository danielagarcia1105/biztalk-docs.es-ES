---
title: Nodo BindingInfo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BindingInfo node [binding file]
ms.assetid: a71d100c-cf8b-4a54-b239-ee0ca2d8148c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dc15cbfe4bb3a98e17a894c5a763c0ca18bdcb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bindinginfo-node"></a>BindingInfo (nodo)
El **BindingInfo** nodo de un archivo de enlace es el nodo raíz de un archivo de enlace y contiene información que se aplica a todas las entradas del archivo de enlace, así como información sobre el servidor de BizTalk que se exportó el archivo de enlace De.  
  
## <a name="nodes-in-the-bindinginfo-node"></a>Nodos del nodo BindingInfo  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Ensamblado|Attribute|xs:string|Especifica información acerca de la dll de Microsoft.BizTalk.Deployment utilizada al crear el archivo de enlace. Consta de los atributos Versión, Referencia cultural y PublicKeyToken para este ensamblado, separados por comas.|Necesario|Valor predeterminado: **"Microsoft.BizTalk.Deployment, Version = 3.0.1.0, Culture = neutral, PublicKeyToken = 31bf3856ad364e35"**|  
|Versión|Attribute|xs:string|Especifica la versión de BizTalk Server con la que se generó el archivo de enlace.|Necesario|Valor predeterminado: **3.5.1.0**|  
|BindingStatus|Attribute|BindingState (SimpleType)|Especifica el estado de enlace de los artefactos exportados con el archivo de enlace.|Necesario|Valor predeterminado: ninguno<br /><br /> Valores válidos:<br /><br /> : Desconocido<br />-NoBindings<br />-Sin enlazar<br />-PartiallyBound<br />-FullyBound|  
|BoundEndpoints|Attribute|xs:int|Especifica el número de extremos enlazados en el archivo de enlace.|Necesario|Valor predeterminado: **0**|  
|TotalEndpoints|Attribute|xs:int|Especifica el número total de extremos del archivo de enlace.|Necesario|Valor predeterminado: **0**|  
|Description|Elemento|xs:string|Proporciona una descripción textual de la sección BindingInfo del archivo de enlace.|No requerido|Valor predeterminado: vacío|  
|Timestamp|Elemento|xs:dateTime|Especifica cuándo se exportó el archivo de enlace.|Necesario|Valor predeterminado: hora que marcaba el servidor de BizTalk cuando se exportó el archivo de enlace.|  
|[ModuleRefCollection (nodo)](../core/modulerefcollection-node.md)|Grabar|ArrayOfModuleRef (ComplexType)|Nodo contenedor de los ensamblados .NET exportados con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|  
|[Nodo SendPortCollection](../core/sendportcollection-node.md)|Grabar|ArrayOfSendPort (ComplexType)|Nodo contenedor de los puertos de envío exportados con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|  
|[Nodo DistributionListCollection](../core/distributionlistcollection-node.md)|Grabar|ArrayOfDistributionList (ComplexType)|Nodo contenedor de las listas de distribución exportadas con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|  
|[Nodo ReceivePortCollection](../core/receiveportcollection-node.md)|Grabar|ArrayOfReceivePort (ComplexType)|Nodo contenedor de los puertos de recepción exportados con el archivo de enlace.|No requerido|Valor predeterminado: ninguno|  
  
 En el siguiente código se muestra el formato XML usado en el nodo BindingInfo de un archivo de enlace:  
  
```  
<BindingInfo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
Assembly="Microsoft.BizTalk.Deployment, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
Version="3.5.1.0" BindingStatus="FullyBound"   
BoundEndpoints="12"   
TotalEndpoints="12">  
<Description/>  
<Timestamp>2005-08-23T16:27:40.5948205-07:00</Timestamp>  
```  
  
## <a name="see-also"></a>Vea también  
 [Personalizar archivos de enlace](../core/customizing-binding-files.md)