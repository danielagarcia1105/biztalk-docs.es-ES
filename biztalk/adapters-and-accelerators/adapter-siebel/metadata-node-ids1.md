---
title: Identificadores de nodo de metadatos para el adaptador de Siebel en BizTalk Adapter Pack | Microsoft Docs
description: Metadatos, búsqueda, tipos de nodos de recuperación y los identificadores usados en componentes de Siebel se exponen en el adaptador de Siebel - módulo de adaptador de BizTalk (BAP)
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
ms.openlocfilehash: abce1288be6c706d71bf644325a9cfd7200155c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991485"
---
# <a name="node-types-and-ids-for-the-siebel-adapter"></a>Tipos de nodo e identificadores para el adaptador de Siebel

## <a name="metadata-node-types-and-ids"></a>Identificadores y tipos de nodo de metadatos 
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] artefactos del sistema de Siebel se manifiesta en forma jerárquica. La tabla siguiente describen los tipos de nodo e identificadores de nodo para los artefactos de Siebel obtenidos por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  


|                Artefacto                 | Tipo de nodo |                                 Id. de nodo                                  |                                          Ejemplo                                          |                                  Descripción                                   |
|-----------------------------------------|-----------|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| Objetos de negocios (todos los objetos de negocio) | CATEGORÍA  |                        [Versión] / BusinessObjects                         |                http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects                |                         Devuelve todos los objetos de negocios.                          |
|          Objeto de negocios (BO)           | CATEGORÍA  |                      /BusinessObjects/ [versión] [BO]                      |            http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account            | Devuelve todos los componentes empresariales asociados con el objeto comercial especificado. |
|         Componente de negocio (BC)         | CATEGORÍA  |                   /BusinessObjects/ [versión] [BO] / [BC]                    |        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account        |    Devuelve todas las operaciones asociadas con el componente empresarial especificado.    |
|                 Insert                  | OPERATION |                /BusinessObjects/ [versión] [BO] / [BC] / inserción                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert     |       Devuelve la operación de inserción para el componente empresarial especificado.       |
|                  Consulta                  | OPERATION |                /BusinessObjects/ [versión] [BO] / [BC] / consulta                 |     http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query     |       Devuelve la operación de consulta para el componente empresarial especificado.        |
|                 Update                  | OPERATION |                /BusinessObjects/ [versión] [BO] / [BC] / actualizar                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update     |       Devuelve la operación de actualización para el componente empresarial especificado.       |
|                 DELETE                  | OPERATION |                /BusinessObjects/ [versión] [BO] / [BC] / Delete                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete     |       Devuelve la operación de eliminación para el componente empresarial especificado.       |
|                Asociar                | OPERATION |              /BusinessObjects/ [versión] [BO] / [BC] / asociar               |   http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate   |     Devuelve la operación de asociación para el componente empresarial especificado.      |
|               Desasociar                | OPERATION |              /BusinessObjects/ [versión] [BO] / [BC] / desasociar              |  http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Dissociate   |     Devuelve la operación de desasociar del componente empresarial especificado.     |
|  Query_ [componente de negocio secundario MVG]   | OPERATION | /BusinessObjects/ [versión] [BO] / [BC] / Query_ [componente de negocio secundario MVG] | http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact |          Devuelve la operación de consulta para el componente empresarial secundario          |
|            Servicios empresariales            | CATEGORÍA  |                        [Versión] / BusinessServices                        |               http://Microsoft.LobServices.Siebel/2007/03/BusinessServices                |                         Devuelve todos los servicios de negocios.                         |
|            Servicio de negocio             | CATEGORÍA  |              /BusinessServices/ [versión] [servicio de negocio]               |             http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP              |        Devuelve todos los métodos de negocio para el servicio de negocio especificados.        |
|         Método de servicio de negocio         | OPERATION | /BusinessServices/ [versión] [servicio de negocio] / [método de servicio de negocio]  |       http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP/ATPRunCheck        |                 Devuelve el método de servicio comercial especificada.                 |

 [Versión] = la cadena de versión; Por ejemplo http://Microsoft.LobServices.Siebel/2007/03.  

 [BO] = objeto de negocios de Siebel A; Por ejemplo, la cuenta.  

 [BC] = un componente empresarial; Por ejemplo, la cuenta.  

 [Servicio de negocio] = Siebel de un servicio de negocio; Por ejemplo, ATP.  

 [Método de servicio de negocio] = un método de un servicio de negocio; Por ejemplo, DismissAlarm.  

 [Componente de negocio secundario MVG] = un componente empresarial de secundarios de grupo de varios valores; Por ejemplo, póngase en contacto con.  

## <a name="metadata-search-and-node-ids"></a>Búsqueda de metadatos y los identificadores de nodo  
 Búsqueda de metadatos es una potente característica que el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] superficies como parte de su **MetadataRetrievalContract** interfaz. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] aprovecha esta característica para admitir la búsqueda de los siguientes artefactos de Siebel.  

|Artefacto|Id. de nodo|Descripción|  
|--------------|-------------|-----------------|  
|Objeto de negocios|[Versión] / BusinessObjects|Devolver los objetos de negocios que coinciden con la expresión de búsqueda.|  
|Componente de negocio|/BusinessObjects/ [versión] [BO]|Devuelve los componentes empresariales que coinciden con la expresión de búsqueda.|  
|Servicio de negocio|[Versión] / BusinessServices|Devolver los servicios de negocios que coinciden con la expresión de búsqueda.|  
|Método de servicio de negocio|/BusinessServices/ [versión] [servicio de negocio]|Devuelve los métodos de servicio empresarial que coinciden con la expresión de búsqueda.|  

 [Versión] = la cadena de versión; Por ejemplo http://Microsoft.LobServices.Siebel/2007/03.  

 [BO] = un objeto de negocios de Siebel; Por ejemplo, la cuenta.  

 [Servicio de negocio] = un servicio empresarial de Siebel; Por ejemplo, ATP.  

 Para las expresiones de búsqueda válidos, consulte la documentación de Siebel.  

> [!NOTE]
>  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] solo admite las búsquedas en el nivel por debajo del nodo actualmente seleccionado.  Por ejemplo, cuando se selecciona BusinessObjects, A * es una búsqueda, pero un\*/A\* no.  

## <a name="metadata-retrieval-and-node-ids"></a>Recuperación de metadatos y los identificadores de nodo  
 El adaptador de Siebel captura las siguientes características para cada tipo de artefacto.  

|Artefacto|Características de los metadatos|  
|--------------|------------------------------|  
|Componente de negocio|<ul><li>Nombre del componente empresarial</li><li>Nombres de campo del componente de negocio</li><li>Tipos de datos de campo de componente de negocio a simple o complejo WSDL tipos asignados</li><li>Longitud de campo del componente empresarial asignado a la faceta maxLength</li><li>Campo obligatorio del componente empresarial asignado a la faceta minOccurs = 1</li><li>Campo opcional del componente empresarial asignado a la faceta minOccurs = 0</li><li>Campo de lista desplegable del componente empresarial asignado a un tipo complejo de la lista desplegable en WSDL</li><li>Estático del componente empresarial limitada la lista desplegable para que contenga una lista enumerada de valores</li><li>Restricción del campo NULL de negocio componente asignado a la faceta isNillable = true</li><li>Operaciones de componentes empresariales<br /><br /> <ul><li>INSERT</li><li>QUERY</li><li>UPDATE</li><li>Delete</li><li>ASOCIAR</li><li>DESASOCIAR</li><li>QUERY_ [MVG secundarios Business Comp] para cada componente empresarial de secundario con el que el componente empresarial tiene una relación m: n</li></ul></li></ul>|  
|Método de servicio de negocio|-Nombre del servicio business<br />: Nombre del método<br />-Método es la operación<br />: Los nombres de parámetro de método<br />-Tipos de datos de parámetro de método asignados a tipos WSDL<br />-Dirección del parámetro Method asignado a la dirección del parámetro WSDL<br />-Orden de los parámetros Method asignado a la secuencia de elementos|  

 Para obtener información detallada sobre el formato de los metadatos que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone para artefactos específicos y las operaciones en el sistema de Siebel, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
