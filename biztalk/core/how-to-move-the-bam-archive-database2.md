---
title: Cómo mover la base de datos2 del archivo BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], migrating
- migrating, Archive database [BAM]
ms.assetid: 88b96dc2-8c9c-43f5-afb9-a937e05de36b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33b09bd4e6563800c70acfae12ff52acc2cb071
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967173"
---
# <a name="how-to-move-the-bam-archive-database"></a>Cómo mover la base de datos de archivo de BAM
Este procedimiento se puede utilizar para mover la base de datos de archivo de BAM a otro servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-move-the-bam-archive-database"></a>Para mover la base de datos de archivo de BAM  
  
1. Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
   1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   2. En el símbolo del sistema, desplácese al directorio siguiente:  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
   3. En el símbolo del sistema, escriba:  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
2. Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos del antiguo servidor.  
  
3. Copie la base de datos de archivo de BAM en el nuevo servidor SQL Server.  
  
4. Siga las instrucciones en libros en pantalla de SQL Server para restaurar la base de datos en el nuevo servidor.  
  
5. Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección ArchivingDatabase DeploymentUnit al nombre del nuevo servidor.  
  
6. Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
7. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
8. En el símbolo del sistema, desplácese al directorio siguiente:  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking  
  
9. En el símbolo del sistema, escriba:  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos de BizTalk Server](../core/moving-biztalk-server-databases.md)