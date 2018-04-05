---
title: Puerto (nodo puertos) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port node [binding file]
ms.assetid: 6c9a3e5f-0b3c-40f8-9a8d-5a83bd559021
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01a808f4415019ba48deb1b3b80ad8aae9e1db04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="port-ports-node"></a>Puerto (nodo Puertos)
El nodo Puerto de un archivo de enlace contiene información específica acerca de un puerto o de una lista de distribución enlazada a un servicio que se exporta con el archivo de enlace.  
  
> [!NOTE]
>  A una lista de distribución se hace referencia como un grupo de puertos de envío en la consola de administración de BizTalk Server.  
  
## <a name="nodes-in-the-port-node"></a>Nodos del nodo Puerto  
 En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:  
  
|**Nombre**|**Tipo de nodo**|**Tipo de datos**|**Description**|**Restricciones**|**Comentarios**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Nombre|Atributo|xs:string|Especifica el nombre del puerto.|No requerido|Valor predeterminado: vacío|  
|Modificador|Attribute|xs:int|Especifica el modificador de tipo para el puerto.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la [Microsoft.BizTalk.ExplorerOM.PortModifier](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.portmodifier.aspx) enumeración.|  
|BindingOption|Attribute|xs:int|Define el tipo de enlace del puerto.|Necesario|Valor predeterminado: ninguno<br /><br /> Los valores posibles incluyen los que están disponibles en la [Microsoft.BizTalk.ExplorerOM.BindingType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.bindingtype.aspx) enumeración.|  
|[SendPortRef](../core/sendportref-port-node.md)|Grabar|SendPortRef (ComplexType)|Nodo contenedor para puertos de envío al que hace referencia un servicio.|No requerido|Valor predeterminado: vacío|  
|[DistributionListRef](../core/distributionlistref-port-node.md)|Grabar|DistributionListRef (ComplexType)|Nodo contenedor para listas de distribución al que hace referencia un servicio.|No requerido|Valor predeterminado: vacío|  
|[ReceivePortRef](../core/receiveportref-port-node.md)|Grabar|ReceivePortRef (ComplexType)|Nodo contenedor para puertos de recepción al que hace referencia un servicio.|No requerido|Valor predeterminado: vacío|