---
title: "Paso 2: Actualizar e implementar la solución del Tutorial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67fd3d34f25dd409121a3a21c9eb419b4aadce6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a>Paso 2: Actualizar e implementar la solución del Tutorial
![Paso 2 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 En este paso actualizará la solución propuesta para este tutorial para, a continuación, generar e implementar el ensamblado del tutorial. Para cumplir los fines de este tutorial, se han creado ya el esquema, la canalización de envío personalizada y la asignación necesarios. La asignación se utiliza para convertir los datos de EDI 850 en el formato necesario según el sistema de pedidos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a>Para habilitar la integración de la solución de procesamiento entrante de EDI en Visual Studio  
  
1.  Iniciar **Microsoft Visual Studio** como administrador.  
  
    > [!CAUTION]
    >  Si no inicia Visual Studio con privilegios de administrador, obtendrá un error cuando implemente la solución para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2.  En Visual Studio, haga clic en **archivo**, seleccione **abiertos**y, a continuación, haga clic en **proyecto/solución**. Mover a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, seleccione **EDI Inbound Processing.sln**y, a continuación, haga clic en **abiertos**.  
  
    > [!NOTE]
    >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
3.  Haga clic en el **Inbound_EDI** del proyecto en el Explorador de soluciones y, a continuación, seleccione **propiedades**.  
  
4.  En el árbol de consola de la **páginas de propiedades de Inbound_EDI** cuadro de diálogo, seleccione **implementación** y en el **Server** campo asegurarte de que se especifique el nombre del equipo.  
  
5.  En el árbol de consola, haga clic en **firma** y, a continuación, seleccione **firmar el ensamblado**. Para **elegir un archivo de nombre de clave seguro**, seleccione \< **nuevo...**  \> y escriba **keyfile.snk** como el **nombre de archivo de clave**. Desactive **proteger mi archivo de clave con una contraseña** y, a continuación, haga clic en **Aceptar**.  
  
6.  Cerrar la **páginas de propiedades de Inbound_EDI** cuadro de diálogo.  
  
### <a name="to-deploy-the-project"></a>Para implementar el proyecto  
  
1.  En el Explorador de soluciones, haga doble clic en el **X12_00401_850.xsd** esquema. Asegúrese de que se abre.  
  
2.  En el Explorador de soluciones, haga doble clic en el **Inbound4010850_to_OrderFile.btm** mapa. Asegúrese de que se abre.  
  
    > [!NOTE]
    >  La asignación Inbound4010850_to_OrderFile.btm del proyecto asigna los datos del mensaje de prueba de 850 entrante al archivo XML saliente que se ha enviado a la carpeta del sistema de pedidos (\toOrderSystem).  
  
3.  En el Explorador de soluciones, haga clic en el **Inbound_EDI** de proyecto y seleccione **generar** para compilar el proyecto.  
  
4.  En el Explorador de soluciones, haga clic en el **Inbound_EDI** de proyecto y seleccione **implementar** para implementar el proyecto.  
  
5.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, \<  **Todos los artefactos** \> y, a continuación, seleccione **recursos**. Compruebe que la **Inbound_EDI** ensamblado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar un perfil de entidad y de negocio para su organización (**OrderSystem**), tal y como se describe en [paso 3: configurar una entidad y perfil de negocio para su organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Prepara el tutorial de programadores de interfaces de EDI](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)