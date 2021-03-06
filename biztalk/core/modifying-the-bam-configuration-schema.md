---
title: Modificación del esquema de configuración de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuration schema [BAM]
- managing [BAM], configuration schema
- BAMConfiguration.xml file
ms.assetid: 8901fb05-1519-4033-8489-67a9b745ed43
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87721445a19cff96799418c019560d09a1287488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263284"
---
# <a name="modifying-the-bam-configuration-schema"></a>Modificar el esquema de configuración de BAM
El Asistente para configuración crea este archivo de configuración automáticamente. Deberá modificar este archivo manualmente si cambia los nombres de servidor u otra información de configuración después de completar la implementación.  
  
> [!NOTE]
>  Para aprobar los cambios realizados en el archivo de configuración de BAM, los administradores deberán anular la implementación de la configuración de BAM actual, y después implementar el archivo BAMConfiguration.xml actualizado.  
  
 Para obtener información acerca de cómo anular la implementación de una definición de BAM, consulte [anular la implementación de las definiciones de BAM](../core/how-to-remove-bam-definitions.md). Para obtener información acerca de cómo implementar una definición de BAM, consulte [implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md).  
  
 A continuación se incluye el esquema que se utiliza para el archivo BAMConfiguration.xml:  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="urn:schemas-microsoft.com:BAM" targetNamespace="urn:schemas-microsoft.com:BAM" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
     <xs:element name="BAMConfiguration">  
          <xs:complexType>  
               <xs:sequence>  
                    <xs:element name="DeploymentUnit" maxOccurs="unbounded" type="DeploymentUnit" />  
               </xs:sequence>  
          </xs:complexType>  
     </xs:element>  
     <xs:complexType name="DeploymentUnit">  
          <xs:sequence>  
               <xs:element name="Property" maxOccurs="unbounded" type="Property" />  
          </xs:sequence>  
          <xs:attribute name="Name" type="xs:string" />  
     </xs:complexType>  
     <xs:complexType name="Property">  
          <xs:simpleContent>  
               <xs:extension base='xs:string'>  
                    <xs:attribute name='Name' type='xs:NCName' />  
               </xs:extension>  
          </xs:simpleContent>  
     </xs:complexType>  
</xs:schema>  
```  
  
 El ejemplo siguiente es un archivo XML que se ajusta al esquema de configuración de BAM.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<BAM:BAMConfiguration xmlns:BAM='urn:schemas-microsoft.com:BAM' xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance'>  
     <DeploymentUnit Name="PrimaryImportDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMPrimaryImport</Property>  
          <Property Name="RTAWindow">60</Property>  
          <Property Name="RTATimeSlice">5</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="StarSchemaDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMStarSchema</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="AnalysisDatabase">  
          <Property Name="ServerName">localhost</Property>  
          <Property Name="DatabaseName">BAMAnalysis</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="ArchivingDatabase">  
          <Property Name="ServerName">.</Property>  
          <Property Name="DatabaseName">BAMArchiving</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="CubeUpdateDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>  
     </DeploymentUnit>  
     <DeploymentUnit Name="DataMaintenanceDTS">  
          <Property Name="ConnectionTimeOut">15</Property>  
          <Property Name="UseEncryption">1</Property>  
          <Property Name="OwnerPassword">myOwnerPassword</Property>  
          <Property Name="UserPassword">myUserPassword</Property>       
     </DeploymentUnit>  
</BAM:BAMConfiguration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de configuración de BAM](../core/bam-configuration-schema.md)   
 [Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md)   
 [Actividad económica (BAM) de supervisión](../core/business-activity-monitoring-bam.md)