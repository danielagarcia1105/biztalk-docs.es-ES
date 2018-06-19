---
title: Los identificadores de nodo de metadatos para el adaptador de BizTalk Adapter Pack | Documentos de Microsoft
description: Metadatos, búsqueda, tipos de nodos de recuperación e identificadores utilizados en componentes de Siebel aparecen en el adaptador de Siebel - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdffc8d1-0a0a-48d7-b134-5d16acf2c523
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5aecf8995b30f5cd545e4202da0c468d730e277
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223388"
---
# <a name="node-types-and-ids-for-the-siebel-adapter"></a>Tipos de nodo e identificadores para el adaptador de Siebel

## <a name="metadata-node-types-and-ids"></a>Tipos de nodos de metadatos e identificadores 
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies artefactos del sistema Siebel de forma jerárquica. La tabla siguiente describen los tipos de nodo e identificadores de nodo para los artefactos de Siebel obtenidos por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
|Artefacto|Tipo de nodo|Id. de nodo|Ejemplo|Description|  
|--------------|---------------|-------------|-------------|-----------------|  
|Objetos de negocios (todos los objetos de negocio)|CATEGORÍA|[Versión] / BusinessObjects|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects|Devuelve todos los objetos de negocios.|  
|Objeto de negocios (BO)|CATEGORÍA|/BusinessObjects/ [versión] [BO]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account|Devuelve todos los componentes empresariales asociados con el objeto comercial especificado.|  
|Componente de negocio (BC)|CATEGORÍA|/BusinessObjects/ [versión] [BO] / [BC]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account|Devuelve todas las operaciones asociadas con el componente empresarial especificado.|  
|Insert|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / inserción|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/INSERT|Devuelve la operación de inserción para el componente de negocio especificados.|  
|Query|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / consulta|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query|Devuelve la operación de consulta para el componente de negocio especificados.|  
|Update|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] o la actualización|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update|Devuelve la operación de actualización para el componente de negocio especificados.|  
|DELETE|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / eliminar|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete|Devuelve la operación de eliminación para el componente de negocio especificados.|  
|Asociar|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / asociado|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate|Devuelve la operación de asociación para el componente de negocio especificados.|  
|Desasociar|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / desasociar|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/DISSOCIATE|Devuelve la operación de desasócielo para el componente de negocio especificados.|  
|Query_ [componente de negocio MVG secundario]|OPERATION|/BusinessObjects/ [versión] [BO] / [BC] / Query_ [componente de negocio MVG secundario]|http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact|Devuelve la operación de consulta para el componente empresarial secundario|  
|Servicios para la empresa|CATEGORÍA|[Versión] / BusinessServices|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices|Devuelve todos los servicios de negocios.|  
|Servicio de negocios|CATEGORÍA|/BusinessServices/ [versión] [servicio de negocio]|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP|Devuelve todos los métodos de negocio para el servicio de negocio especificados.|  
|Método de servicio de negocios|OPERATION|/BusinessServices/ [versión] [servicio de negocio] / [método de servicio de negocio]|http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP/ATPRunCheck|Devuelve el método de servicio de negocio especificados.|  
  
 [Versión] = la cadena de versión; Por ejemplo http://Microsoft.LobServices.Siebel/2007/03.  
  
 [BO] = objeto de negocios de Siebel A; Por ejemplo, la cuenta.  
  
 [BC] = un componente empresarial; Por ejemplo, la cuenta.  
  
 [Servicio de negocio] = servicio de negocios de Siebel A; Por ejemplo, ATP.  
  
 [Método de servicio de negocio] = un método de un servicio empresarial; Por ejemplo, DismissAlarm.  
  
 [Componente de negocio de MVG secundario] = un componente empresarial de secundarios de grupo de varios valores; Por ejemplo, póngase en contacto con.  
  
## <a name="metadata-search-and-node-ids"></a>Búsqueda de metadatos y los identificadores de nodo  
 Búsqueda de metadatos es una eficaz característica que el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] superficies como parte de su **MetadataRetrievalContract** interfaz. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] aprovecha esta característica para admitir la búsqueda de los siguientes artefactos de Siebel.  
  
|Artefacto|Id. de nodo|Description|  
|--------------|-------------|-----------------|  
|Objeto de negocios|[Versión] / BusinessObjects|Devolver los objetos de negocios que coinciden con la expresión de búsqueda.|  
|Componente empresarial|/BusinessObjects/ [versión] [BO]|Devolver los componentes empresariales que coincide con la expresión de búsqueda.|  
|Servicio de negocios|[Versión] / BusinessServices|Devolver los servicios de negocios que coinciden con la expresión de búsqueda.|  
|Método de servicio de negocios|/BusinessServices/ [versión] [servicio de negocio]|Devolver los métodos de servicio de negocio que coinciden con la expresión de búsqueda.|  
  
 [Versión] = la cadena de versión; Por ejemplo http://Microsoft.LobServices.Siebel/2007/03.  
  
 [BO] = un objeto de negocios de Siebel; Por ejemplo, la cuenta.  
  
 [Servicio de negocio] = un servicio de negocios de Siebel; Por ejemplo, ATP.  
  
 Para las expresiones de búsqueda válidos, consulte la documentación de Siebel.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] sólo es compatible con las búsquedas en el nivel por debajo del nodo seleccionado actualmente.  Por ejemplo, cuando se selecciona BusinessObjects, un * es compatible búsqueda, pero A\*/A\* no es.  
  
## <a name="metadata-retrieval-and-node-ids"></a>Recuperación de metadatos y los identificadores de nodo  
 El adaptador de Siebel captura las siguientes características para cada tipo de artefacto.  
  
|Artefacto|Características de los metadatos|  
|--------------|------------------------------|  
|Componente empresarial|<ul><li>Nombre de componente de negocio</li><li>Nombres de campo del componente de negocio</li><li>Tipos de datos de campo de componente de negocio que asignan a WSDL simple o complejo tipos</li><li>Longitud de campo del componente empresarial asignado a maxLength de faceta</li><li>Campo obligatorio del componente empresarial asignado a la faceta minOccurs = 1</li><li>Campo opcional del componente empresarial asignado a la faceta minOccurs = 0</li><li>Campo de lista desplegable del componente empresarial asignado a un tipo complejo de lista de selección en WSDL</li><li>Estático de componente de negocio limitado lista desplegable para que contenga una lista enumerada de valores</li><li>Restricción del campo NULL de negocio componente asignado a la faceta isNillable = true</li><li>Operaciones de componentes empresariales<br /><br /> <ul><li>INSERT</li><li>QUERY</li><li>UPDATE</li><li>DELETE</li><li>ASOCIAR</li><li>DESASOCIAR</li><li>QUERY_ [MVG secundarios Business Comp] para cada componente empresarial de secundario con la que el componente empresarial tiene una relación m: n</li></ul></li></ul>|  
|Método de servicio de negocios|-Nombre del servicio business<br />: Nombre del método<br />-Method es la operación<br />: Nombres de parámetros de método<br />-Tipos de datos de parámetro de método asignados a tipos WSDL<br />-Dirección del parámetro Method asignado a la dirección del parámetro WSDL<br />-Orden de los parámetros Method asignado a la secuencia de elementos|  
  
 Para obtener información detallada sobre el formato de los metadatos que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone para artefactos específicos y operaciones en el sistema Siebel, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
  