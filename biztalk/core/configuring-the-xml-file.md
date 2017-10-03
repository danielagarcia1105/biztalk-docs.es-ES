---
title: Configurar el archivo XML. | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d791de9b6fe90ebb850874026e8d52e49732f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-xml-file"></a>Configurar el archivo XML
Si se instala Inicio de sesión único empresarial (SSO), un archivo XML denominado ENTSSO.xml se instalará en el directorio de extensiones. Al editar el archivo, se define la configuración para todas las instancias del agente de administración de ENTSSO (MA).  
  
 El archivo es similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a>Elementos y atributos XML  
 La siguiente lista describe los elementos y atributos que se definen en el archivo XML. Tenga en cuenta que todos los nombres de elementos y atributos de ese archivo distinguen mayúsculas de minúsculas.  
  
 **Elemento: ENTSSO** -define la configuración de una única instancia MA de ENTSSO. Se permiten varios elementos ENTSSO.  
  
 **Atributo: nombre** : define el nombre de instancia del agente de administración de ENTSSO y debe coincidir con el nombre de la instancia de agente de administración de ENTSSO en Microsoft Identity Integration Server (MIIS).  
  
 **Atributo: adma** -define el nombre de instancia del agente de administración de Active Directory que se usará en esta instancia de agente de administración de ENTSSO. El agente de administración de Active Directory proporciona el nombre de dominio de Windows y el nombre de usuario de Windows para la asignación. Este nombre de instancia del agente de administración de Active Directory debe coincidir con el nombre de una instancia del agente de administración de Active Directory en MIIS.  
  
 **Atributo: deleteAll** - opcional; valor predeterminado es `true`. Si se establece como `true` y se elimina una identidad de Windows, se eliminarán todas las asignaciones con dicha identidad de Windows de todas las aplicaciones ENTSSO.  
  
 **Elemento: Aplicación** -define la relación entre una aplicación afiliada SSO y un agente de administración externo. Se permiten varios elementos `Application`.  
  
 **Atributo: nombre** -define el nombre de la aplicación afiliada SSO. Esta aplicación ya debe existir en el sistema ENTSSO.  
  
 **Atributo: sourceMA** -define el nombre de instancia para el origen (externo) agente de administración que se usará para proporcionar el UserId externo en la asignación para esta aplicación. Este nombre de instancia del agente de administración externo debe coincidir con el nombre de una instancia de MA externa en MIIS.  
  
 **Atributo: crear** - opcional; valor predeterminado es `true`. Define si se deben crear asignaciones para esta aplicación.  
  
 **Atributo: eliminar** - opcional; valor predeterminado es `true`. Define si se deben eliminar asignaciones para esta aplicación.  
  
 **Elemento: SourceMA** : opcional. Identifica el tipo de objeto y los nombres de atributo para una instancia del agente de administración de origen específico (externo). Si este elemento no está presente para un agente de administración específico, se consideran el tipo de objeto predeterminado (“person”) y los nombres de atributos (“uid”). Se permiten varios elementos `SourceMA`.  
  
 **Atributo: nombre** -el nombre del origen (externo) de agente de administración. Este nombre debe coincidir como mínimo con uno de los `sourceMA` nombres de atributos de los elementos `Application`.  
  
 **Atributo: objectType** - opcional; valor predeterminado es `person`. Si el nombre del tipo de objeto que proporciona el UserId externo no es `person`, debe especificarse aquí.  
  
 **Atributo: atributo** - opcional; valor predeterminado es `uid`. Si el nombre del atributo que proporciona el UserId externo no es `uid`, puede especificarlo aquí.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar al agente de administración de ENTSSO](../core/how-to-use-the-entsso-management-agent.md)