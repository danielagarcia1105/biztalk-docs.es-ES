---
title: Esquema de mensaje para las operaciones de lista desplegable | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- picklist operations, message schemas for
- picklist operations, message actions
- picklist operations, message
ms.assetid: c0b62a8c-5a68-47ea-8676-1580601b5ec9
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d72a16e99e38649a6fb8d74178d2b5da1d059dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221908"
---
# <a name="message-schema-for-picklist-operations"></a>Esquema de mensaje para las operaciones de lista de selección
Listas desplegables son tipos de campo especial en los componentes empresariales. Representan una colección de valores desde el que un usuario puede elegir un valor único para la asignación. Listas desplegables son de tipos diferentes. Para obtener más información sobre las listas desplegables y sus tipos, consulte la documentación de Siebel.  
  
 Uno de los tipos de lista de selección, listas desplegables enlazados estáticos, se producen por los adaptadores de como una lista de selección enumerado tipo en los metadatos generados por el adaptador en tiempo de diseño. Contiene un conjunto estático de valores que debe especificarse para el tipo de lista de selección en tiempo de ejecución.  Al especificar un valor de una lista de desplegable enlazado estática, siempre debe especificar un valor que pertenece al conjunto.  
  
 El ejemplo siguiente muestra el esquema de un tipo de lista desplegable enlazado estático:  
  
```  
<element name="[FIELD_NAME]RequiredPickListType" nillable="true" type="ns1:[FIELD_NAME]RequiredPickListType" />  
<simpleType name="[FIELD_NAME]RequiredPickListType">  
<restriction base="string">  
  <enumeration value="value1" />  
  <enumeration value="value2" />  
  …  
</restriction>  
</simpleType>  
```  
  
 [Nombre_de_campo] = nombre de campo de lista desplegable en el componente empresarial  
  
 El siguiente ejemplo representa la experiencia de proxy de un tipo de lista desplegable enlazado estático:  
  
```  
[BC]InsertRecord[] insertRecs = new [BC]InsertRecord[1];  
insertRecs[0] = new [BC]InsertRecord();  
insertRecs[0].[BC_STATIC_PICKLIST_FIELD] = [BC_PICKLIST_FIELD_NAME]OptionalPickListType.value1;  
```  
  
 [BC_STATIC_PICKLIST_FIELD] = un campo estático de lista de selección limitada de la continuidad del negocio  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)