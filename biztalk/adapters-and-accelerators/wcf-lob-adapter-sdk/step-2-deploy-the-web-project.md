---
title: 'Paso 2: Implementar el proyecto Web | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 503ce37fd06f91d5036f08c9eee752017c0ad21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-deploy-the-web-project"></a>Paso 2: Implementar el proyecto Web
![Paso 2 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **Tiempo en completarse:** 5 minutos  
  
 En este paso se publicará el proyecto Web generado en [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md) para Internet Information Services (IIS).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para completar este paso, debe haber completado [paso 1: usar el Asistente para desarrollo de servicio de adaptador para crear el proyecto Web](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md). El servidor Web también debe tener un certificado SSL instalado para habilitar la comunicación HTTPS.  
  
### <a name="to-compile-and-deploy-the-web-project"></a>Para compilar e implementar el proyecto Web  
  
1.  En [!INCLUDE[vs2010](../../includes/vs2010-md.md)], cargar el proyecto EchoWeb que creó anteriormente.  
  
2.  Abra un [!INCLUDE[vs2010](../../includes/vs2010-md.md)] símbolo del sistema.  
  
3.  En el símbolo del sistema, desde la carpeta C:\tutorials\echoweb, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
     **sn /k EchoWebKey.snk**  
  
     Un mensaje de confirmación, **clave par escrito en EchoWebKey.snk**, se muestra en la línea de comandos.  
  
4.  Cierre el símbolo del sistema.  
  
5.  En **el Explorador de soluciones**, haga clic en el proyecto de EchoWeb y, a continuación, seleccione **Publicar sitio Web**.  
  
6.  En el **Publicar sitio Web** cuadro de diálogo para **ubicación de destino**, escriba **http://machinename/EchoWeb**. Seleccione **permitir que este sitio precompilado se actualizables**, **uso corregido únicos y nomenclatura de ensamblados de página**, y **habilitar nombres seguros en los ensamblados precompilan**. En el **ubicación del archivo de clave** , a continuación, haga clic en los puntos suspensivos **(...)**  botón, seleccione el archivo EchoWebKey.snk creado anteriormente y, a continuación, haga clic en **Aceptar**.  
  
7.  Para comprobar que el sitio Web se ha creado correctamente, inicie Internet Explorer, escriba **HYPERLINK "http://localhost/EchoWeb/EchoOutboundContract.svc" http://localhost/EchoWeb/EchoOutboundContract.svc** en la barra de direcciones, y a continuación, presione ENTRAR. Debe aparecer una página Web que describe la EchoOutboundContractClient.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Acaba de publicar el proyecto Web en IIS.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Ahora que ha compilado e implementado el proyecto, puede continuar con [paso 3: crear un archivo de definición de aplicación](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Aloja el adaptador de eco en IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)