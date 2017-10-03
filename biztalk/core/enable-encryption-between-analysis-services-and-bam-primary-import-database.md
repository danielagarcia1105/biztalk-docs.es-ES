---
title: "Cómo habilitar el cifrado entre Analysis Services y la base de datos de importación principal de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77069c3690a73957936c786bc05c2690b9df7a10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a>Cómo habilitar el cifrado entre los servicios de análisis y la base de datos de importación principal de BAM
El cifrado no se habilita de forma predeterminada durante una instalación o actualización de BAM. Para habilitar el cifrado, deberá definir la marca UseEncryption del archivo XML de configuración de BAM con el valor 1.  
  
 También deberá habilitar el cifrado en los servicios de análisis de SQL Server. Para obtener más información acerca de cómo habilitar el cifrado, vea [proteger la comunicación del cliente con una instancia de Analysis Services](http://go.microsoft.com/fwlink/?LinkId=190805) (http://go.microsoft.com/fwlink/?LinkId=190805).  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a>Para habilitar el cifrado entre SQL Server Analysis Services y la base de datos de importación principal de BAM  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  Navegue a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  
3.  Tipo de **bm get-config - FileName:\<archivo de salida >**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Presione **ENTRAR**.  
  
5.  En un editor de texto, abra el archivo de configuración que ha exportado, y cambie a 1 el valor de la marca de propiedad UseEncryption.  
  
    -   Valor predeterminado: \<nombre de propiedad = "UseEncryption" > 0 \< /Property >  
  
    -   Nueva configuración: \<nombre de propiedad = "UseEncryption" > 1 \< /Property >  
  
6.  Actualizar la configuración de BAM escribiendo **bm update-config - FileName:\<el archivo de configuración >**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)