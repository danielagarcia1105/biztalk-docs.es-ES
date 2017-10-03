---
title: 'Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9654f295f0f43b720b7ac77aec4ac6315f78ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a>Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, generará e implementará el proyecto de BizTalk vPrev existente para recibir un IDOC desde un sistema SAP.  
  
> [!NOTE]
>  No es necesario realizar ningún cambio en el proyecto de BizTalk vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener un proyecto de BizTalk vPrev para recibir un IDOC ORDERS03 desde un sistema SAP.  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>Para compilar e implementar el proyecto de BizTalk vPrev  
  
1.  Crear un archivo de clave de nombre seguro necesario para compilar e implementar la solución. Para crear un archivo de clave de nombre seguro, haga lo siguiente:  
  
    1.  Inicie el símbolo del sistema de Visual Studio.  
  
    2.  En el símbolo del sistema navegue hasta la carpeta donde desea crear el archivo de clave. Por ejemplo, escriba **cd C:\Sample**, y, a continuación, presione ENTRAR.  
  
    3.  En el símbolo del sistema, escriba **sn -k \<nombre de archivo de clave > .snk**, y, a continuación, presione ENTRAR.  
  
2.  Haga clic en el nombre de la solución de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en **propiedades de configuración** en el panel izquierdo y asegúrese de que las casillas de verificación la **generar** y **implementar** se seleccionan las columnas.  
  
    2.  Haga clic en **Aceptar**.  
  
3.  Haga clic en el proyecto de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:  
  
    1.  En el panel izquierdo, expanda **propiedades comunes**y, a continuación, haga clic en ensamblado.  
  
    2.  En el panel derecho, en la **nombre seguro** categoría, para el **archivo de clave de ensamblado** propiedad, proporcione la ruta de acceso al archivo de clave de ensamblado que creó anteriormente.  
  
    3.  Haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.  
  
5.  Después de que la solución se compila correctamente, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear y configurar un WCF-Custom puerto de recepción y configúrelo para recibir IDOC desde un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], tal y como se describe en [paso 2: configurar un puerto de recepción unidireccional de WCF-Custom](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)