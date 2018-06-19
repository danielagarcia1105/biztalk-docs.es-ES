---
title: 'Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para enviar un IDOC | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for sending an IDOC
- migration
ms.assetid: 1982b318-45d1-464e-b7e4-65d459c439e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b9089e90fc3a429d6d594a18b0e1fb6e94d4f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216892"
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc"></a>Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para enviar un IDOC
![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, generará e implementará el proyecto de BizTalk vPrev existente para enviar un IDOC a un sistema SAP.  
  
> [!NOTE]
>  No es necesario realizar ningún cambio en el proyecto de BizTalk vPrev.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe tener un proyecto de BizTalk vPrev para enviar un IDOC BOMDOC a un sistema SAP.  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>Para compilar e implementar el proyecto de BizTalk vPrev  
  
1.  Crear un archivo de clave de nombre seguro necesario para compilar e implementar la solución. Para crear un archivo de clave de nombre seguro, haga lo siguiente:  
  
    1.  Inicie el símbolo del sistema de Visual Studio.  
  
    2.  En el símbolo del sistema navegue hasta la carpeta donde desea crear el archivo de clave. Por ejemplo, escriba **cd C:\Sample**, y, a continuación, presione ENTRAR.  
  
    3.  En el símbolo del sistema, escriba **sn -k \<nombre de archivo de clave > .snk**, y, a continuación, presione ENTRAR.  
  
2.  Haga clic en el nombre de la solución de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:  
  
    1.  Haga clic en Propiedades de configuración en el panel izquierdo y asegúrese de que las casillas de verificación en la **generar** y **implementar** se seleccionan las columnas.  
  
    2.  Haga clic en **Aceptar**.  
  
3.  Haga clic en el proyecto de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:  
  
    1.  En el panel izquierdo, expanda **propiedades comunes**y, a continuación, haga clic en ensamblado.  
  
    2.  En el panel derecho, en la **nombre seguro** categoría, para el **archivo de clave de ensamblado** propiedad, proporcione la ruta de acceso al archivo de clave de ensamblado que creó anteriormente.  
  
    3.  Haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.  
  
5.  Después de que la solución se compila correctamente, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear y configurar un puerto de envío WCF-Custom y configurarlo para enviar los IDOC a un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], tal y como se describe en [paso 2: configurar un puerto de envío unidireccional de WCF-Custom](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Migrar un proyecto de BizTalk SAP IDOC de envío](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)