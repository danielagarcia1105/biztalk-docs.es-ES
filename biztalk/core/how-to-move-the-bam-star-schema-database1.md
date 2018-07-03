---
title: Cómo mover la base de datos1 del esquema de estrella de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3068c9d1c72c30c51f77d9fad7b8ddf5881ed09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983413"
---
# <a name="how-to-move-the-bam-star-schema-database"></a>Cómo mover la base de datos de esquema de estrella de BAM
Este procedimiento se puede utilizar para mover la base de datos de esquema de estrella de BAM a otro servidor.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-move-the-bam-star-schema-database"></a>Para mover la base de datos de esquema de estrella de BAM  
  
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
  
2. Siga las instrucciones en libros en pantalla de SQL Server sobre cómo realizar una copia de seguridad de la base de datos en el servidor anterior.  
  
3. Copie la base de datos de esquema de estrella de BAM en el nuevo servidor SQL Server.  
  
4. Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos en el servidor nuevo.  
  
5. Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección StarSchemaDatabase DeploymentUnit al nombre del nuevo servidor.  
  
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
  
10. Actualice la conexión 2 de SQL para cambiar el nombre de la base de datos y del servidor en todos los paquetes DTS de análisis de BAM, a los que se agrega el prefijo "BAM_AN_" mediante los pasos que se indican a continuación:  
  
    1.  Abra el servidor que hospeda BAM mediante SQL Server Management Studio.  
  
    2.  Abra el **Data Transformation Services** carpeta.  
  
    3.  Abra el **paquetes locales** carpeta.  
  
    4.  Abra el paquete DTS y, a continuación, haga doble clic en **conexión 2** para abrir la conexión.  
  
    5.  Seleccione el nuevo nombre de base de datos y servidor en el cuadro desplegable.  
  
11. Actualice el origen de datos en la base de datos de análisis de BAM del modo siguiente:  
  
    1.  Abra el servidor que aloja la base de datos de análisis de BAM mediante Analysis Manager de SQL Server.  
  
    2.  Abra el **orígenes de datos** carpeta.  
  
    3.  Haga clic en el origen de datos para el cubo y, a continuación, haga clic en **editar**.  
  
    4.  En el **conexión** pestaña, escriba el nuevo nombre del servidor y el nombre de la base de datos para la base de datos de esquema de estrella de BAM y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos de BizTalk Server](../core/moving-biztalk-server-databases.md)