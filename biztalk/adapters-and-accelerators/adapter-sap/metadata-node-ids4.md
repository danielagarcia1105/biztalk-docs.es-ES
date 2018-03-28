---
title: Los identificadores de nodo de metadatos para el adaptador de mySAP en BizTalk Adapter Pack | Documentos de Microsoft
description: Metadatos, búsqueda, tipos de nodos de recuperación e identificadores utilizados en los componentes SAP que se exponen en el adaptador de mySAP - módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46385060-f56a-4e06-9122-b75808776716
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138e46b198df48348dcef35662589f6a3c2e317a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="node-types-and-ids-for-the-sap-adapter"></a>Tipos de nodo e identificadores para el adaptador SAP

## <a name="metadata-node-types-and-ids"></a>Tipos de nodos de metadatos e identificadores
La tabla siguiente enumera el tipo de nodo y el identificador de nodo para los artefactos SAP que la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] superficies. El identificador de nodo es la ruta de acceso absoluta del nodo que se usa en la **IMetadataRetrievalContractBrowse**, **búsqueda**, y **GetMetadata** métodos.  
  
|Nombre para mostrar artefacto|Tipo de nodo|Id. de nodo|  
|---------------------------|---------------|-------------|  
|RFC|CATEGORÍA|[VERSIÓN] / RFCSECTION|  
|[RFC_APPL_GROUP_NAME]|CATEGORÍA|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_ID]|  
|[RFC_NAME]|OPERATION|[VERSION]/Rfc/[RFC_NAME]|  
|RfcGetAttributes|OPERATION|[VERSION]/RfcApi/RfcGetAttributes|  
|TRFC|CATEGORÍA|[VERSIÓN] / TRFCSECTION|  
|[TRFC_APPL_GROUP_NAME]|CATEGORÍA|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_ID]|  
|[TRFC_NAME]|OPERATION|[VERSION]/TRfc/[TRFC_NAME]|  
|RfcConfirmTransID|OPERATION|[VERSION]/RfcApi/RfcConfirmTransID|  
|BAPI|CATEGORÍA|[VERSIÓN] / BAPISECTION/000001|  
|[BAPI_APPL_GROUP_NAME]|CATEGORÍA|/BAPISECTION/ [VERSIÓN] [BAPI_APPL_GROUP_NODE_ID]|  
|[BUSINESS_OBJECT_NAME]|CATEGORÍA|[VERSION]/BAPIOBJ/[BUSOBJ_TYPE]|  
|[BUSINESS_OBJECT_METHOD]|OPERATION|[VERSION]/BAPIOBJ/[BUSOBJ_TYPE]/[BUSOBJ_METHOD]/[FUNCTION_MODULE]|  
|IDOC|CATEGORÍA|[VERSIÓN] / IDOCSECTION|  
|[IDOC_MSG_TYPE_NAME]|CATEGORÍA|[VERSION]/IDOCMESTYP/[IDOC_MSG_TYPE_NAME]|  
|([IDOC_TYPE_NAME]) ([IDOC_CIMTYPE])|CATEGORÍA|[VERSION]/IDOCCIMTYP/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[FIRST_IDOC_REL_NO]|  
|([IDOC_TYPE_NAME].V[IDOC_VERSION]) ([IDOC_CIMTYPE]) ([IDOC_REL_NO])|CATEGORÍA|[VERSION]/IDOCCIMVER/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]|  
|Send|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Send|  
|SendIdoc|OPERATION|[VERSION]/Idoc/SendIdoc|  
|Receive|OPERATION|[VERSION]/Idoc/[IDOC_VERSION]/[IDOC_TYPE_NAME]/[IDOC_CIMTYPE]/[IDOC_REL_NO]/Receive|  
|ReceiveIdoc|OPERATION|[VERSION]/Idoc/ReceiveIdoc|  
  
 [Versión] = la cadena de versión; Por ejemplo, http://Microsoft.LobServices.Sap/2007/03.  
  
 [RFC_APPL_GROUP_NAME] = el nombre de un grupo de aplicación; Por ejemplo, ventas.  
  
 [RFC_APPL_GROUP_ ID] = el identificador asociado a un grupo de aplicaciones de SAP; Por ejemplo, V (de ventas).  
  
 [RFC_NAME] = el nombre de una solicitud de cambio; Por ejemplo, RFC_GET_SYSTEM_INFO.  
  
 [TRFC_APPL_GROUP_NAME] = el nombre de un grupo de aplicación; Por ejemplo, ventas. Este es el nombre del grupo de aplicación para las solicitudes de cambio.  
  
 [TRFC_APPL_GROUP_ ID] = el identificador asociado a un grupo de aplicaciones de SAP; Por ejemplo, V (de ventas). Este es el mismo que el identificador de RFC.  
  
 [TRFC_NAME] = el nombre de un tRFC; Por ejemplo, RFC_GET_SYSTEM_INFO. Este es el mismo que el nombre RFC.  
  
 [BAPI_APPL_GROUP_NAME] = el nombre del grupo BAPI como en el Explorador de BAPI en SAP. Por ejemplo, ventas y distribución.  
  
 [BAPI_APPL_GROUP_NODE_ID] = identificador asociado al nodo correspondiente en el árbol del explorador BAPI en SAP; Por ejemplo, 3253 para ventas y la distribución. Tenga en cuenta que podría haber más nodos de grupo en un nodo de grupo determinado de BAPI. Por ejemplo, las ventas y la distribución de nodo tiene otro nodo de grupo en él denominado ventas (nodo 3375 de Id.).  
  
 [BUSINESS_OBJECT_NAME] = el nombre de un objeto de negocios; Por ejemplo, pedido de venta.  
  
 [BUSOBJ_TYPE] = el tipo de objeto de negocios en SAP; Por ejemplo, BUS2032 para el objeto de negocios de pedido de venta.  
  
 [BUSINESS_OBJECT_METHOD] = el nombre de un método de objeto comercial; Por ejemplo, el método GETLIST para el objeto de negocios de pedido de venta.  
  
 [Función MODULE] = SAP el módulo de función para el método del objeto comercial; Por ejemplo, BAPI_SALESORDER_GETLIST para método GETLIST del objeto de negocios de pedido de venta.  
  
 [IDOC_MSG_TYPE_NAME] = el nombre de un tipo de mensaje IDOC; Por ejemplo, pedidos.  
  
 [IDOC_TYPE_NAME] = el nombre del tipo IDOC; Por ejemplo, ORDERS05.  
  
 [IDOC_CIMTYPE] = el tipo de CIM de IDOC (extensión); Por ejemplo, Z1ORDERS.  
  
 [FIRST_IDOC_REL_NO] = el número de versión IDOC mínimo para un determinado tipo IDOC; Por ejemplo, 46 para ORDERS05 en un sistema SAP determinado.  
  
 [IDOC_VERSION] = número de versión de lanzamiento del IDOC; 2 para la versión 2 IDOC y 3 para la versión 3 IDOC...  
  
 [IDOC_REL_NO] = IDOC el número de versión; Por ejemplo, 46, 46 ter o 620.  
  
## <a name="metadata-search-node-ids"></a>Identificadores de nodo de búsqueda de metadatos  
 Búsqueda de metadatos es una eficaz característica que el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] superficies como parte de su **IMetadataRetrievalContract** interfaz. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa esta característica para admitir la búsqueda de los siguientes artefactos SAP.  
  
|Nombre para mostrar artefacto|Id. de nodo|Description|  
|---------------------------|-------------|-----------------|  
|/RFC|[VERSIÓN] / RFCSECTION|Devolver todas las operaciones de RFC que coinciden con la expresión de búsqueda.|  
|/RFC/[RFC_APPL_GROUP_NAME]|[VERSION]/RFCGROUP/[RFC_APPL_GROUP_NAME]|Devolver RFC operaciones en el grupo de aplicaciones que coinciden con la expresión de búsqueda.|  
|/TRFC|[VERSIÓN] / TRFCSECTION|Devolver todas las operaciones de RFC que coinciden con la expresión de búsqueda.|  
|/TRFC/[TRFC_APPL_GROUP_NAME]|[VERSION]/TRFCGROUP/[TRFC_APPL_GROUP_NAME]|Devolver RFC operaciones en el grupo de aplicaciones que coinciden con la expresión de búsqueda.|  
|/BAPI|[VERSIÓN] / BAPISECTION|Devolver todos los BAPI que coinciden con la expresión de búsqueda.|  
|/IDOC|[VERSIÓN] / IDOCSECTION|Devolver todos los IDOC que coinciden con la expresión de búsqueda.|  
  
 La siguiente tabla muestra el carácter comodín los caracteres que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite en expresiones de búsqueda.  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|signo más (+)|Coincide exactamente con un carácter.<br /><br /> Por ejemplo, A + coincide con AB, CA, AD, y así sucesivamente.|  
|asterisco (*)|Coincide con cero o más caracteres; Por ejemplo, "A *" coincide con "A", "AB", "ABC" y así sucesivamente.|  
  
## <a name="metadata-retrieval-node-ids"></a>Identificadores de nodo de recuperación de metadatos  
 En la tabla siguiente se resume las características de los metadatos devueltas por [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
|Artefacto|Características de los metadatos|  
|--------------|------------------------------|  
|RFC|-Nombre RFC.<br />-Parámetros de importación, exportación, cambiar y tabla RFC.<br />-Tipos de datos del parámetro RFC.<br />-Longitud de campo de parámetro RFC asignado a maxLength de faceta<br />-Parámetro obligatorio RFC asignado a la faceta minOccurs = 1<br />-Parámetro opcional de RFC asignado a la faceta minOccurs = 0<br />-Parámetro RFC asignado a isNillable de faceta de restricción NULL = true. Esto significa que el adaptador no debe pasar este parámetro al sistema SAP.<br />-La RFC propio es la operación.|  
|TRFC|Igual a RFC excepto<br /><br /> -Parámetros de importación RFC no aparecen. Dado que tRFC es asincrónico, no se exponen ningún parámetro de salida.|  
|BAPI|-Nombre de objeto de negocios<br />-Nombre del método de objeto de negocios<br />-Igual que las características RFC|  
|IDOC|Tipo IDOC<br /><br /> CIMType<br /><br /> Número de versión IDOC<br /><br /> Versión IDOC<br /><br /> Campos de registro de control IDOC asignados a un tipo complejo de EDI_DC<br /><br /> Registro de datos de IDOC segmentos y campos del segmento asignados a un tipo complejo de EDI_DD<br /><br /> Relaciones de elementos primarios y secundarios de segmento<br /><br /> Parámetro obligatorio del segmento IDOC asignado a minOccurs = 1<br /><br /> IDOC segmento parámetro opcional que se asignan a minOccurs = 0<br /><br /> Nombre del campo de encabezado de segmento IDOC<br /><br /> Tipo de datos de campo de encabezado de segmento IDOC<br /><br /> Nombre del campo de segmento IDOC<br /><br /> Tipo de datos de campo de segmento IDOC<br /><br /> Enumeraciones de valor de campo de segmento IDOC<br /><br /> IDOC segmento campo valores mínimo y máximo (intervalos) **Nota:** campo de segmento de IDOC an cuando contiene una lista de los valores min, aparece como una enumeración. Si el campo de segmento IDOC contiene los valores mínimo y máximo, aparece como una cadena sin las construcciones de enumeración o el intervalo.|  
  
 Para obtener información detallada sobre el formato de los metadatos que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone para artefactos específicos y operaciones en el sistema SAP, consulte [mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).  
  
