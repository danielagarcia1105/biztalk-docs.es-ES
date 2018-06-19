---
title: Modificar una PIP existente en Rnpip | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNPIPs
- modifying, PIPs
- PIPs, modifying
- assemblies, RNPIPs
ms.assetid: f2ed25c4-1979-4691-9315-e7568e7cca8b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7f87d9af24e6388199e76e9cbf0eba076ceacf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006293"
---
# <a name="modifying-an-existing-pip-in-rnpips"></a>Modificar una PIP existente en Rnpip
Este tema describe cómo cambiar y volver a implementar uno de los esquemas de proceso de interfaz de socio (PIP) instalados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] el programa de instalación. El esquema se implementa como parte del ensamblado de los RNPIP.  
  
### <a name="to-modify-an-existing-pip-in-rnpips"></a>Para modificar un PIP existente en los RNPIP  
  
1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  Busque la \< *unidad*\>\Program BizTalk \<versión\> Acelerador para carpeta RosettaNet\SDK\Utilities\Schema Generator.  
  
3.  En el símbolo del sistema, escriba **CScript InstallDTD.vbs**y presione ENTRAR.  
  
    > [!NOTE]
    >  Solo tienes que realice los pasos 1 y 2 una vez después de instalar a BizTalk Server.  
  
4.  Inicie **Microsoft Visual Studio 2012**.  
  
5.  En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
6.  En el **Abrir proyecto** cuadro de diálogo, desplácese a \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Esquemas y, a continuación, seleccione **RNPIPs.btproj**.  
  
7.  En el menú **Ver** , haga clic en **Explorador de BizTalk**. Expanda **Ensamblados**y, a continuación, haga clic con el botón derecho en **Microsoft.Solutions.BTARN.Schemas.RNPIPs(3.3.0.0)**. Haga clic en **Anular la implementación**.  
  
8.  Inicie un **símbolo del sistema de Visual Studio 2012**.  
  
9. Vaya a la ubicación especificada en el paso 6, en el símbolo del sistema escriba **sn -k RNPIPs.snk**y, a continuación, presione **ENTRAR**.  
  
10. En el Explorador de soluciones, haga clic con el botón derecho en **RNPIP**, haga clic en **Propiedades**, en **Propiedades comunes**y en **Ensamblado.**  
  
11. En el panel derecho, desplácese hacia abajo hasta **Nombre seguro**, en la sección **Archivo de clave de ensamblado** haga clic en el botón de puntos suspensivos (...), vaya a la ubicación especificada en el paso 6, en el símbolo del sistema escriba **RNPIPs.snk**y, a continuación, haga clic en **Aceptar**.  
  
12. En el cuadro de diálogo **Páginas de propiedades** , haga clic en **Propiedades de configuración**, en **Implementación**, en **Volver a implementar**, seleccione `True`y haga clic en **Aceptar**.  
  
13. Edite los esquemas existentes en los RNPIP, si es necesario.  
  
14. Haga clic en **Archivo**y, a continuación, en **Guardar**.  
  
15. Haga clic con el botón derecho en el nombre del proyecto y haga clic en **Compilar**.  
  
16. Haga clic con el botón derecho en el nombre del proyecto y haga clic en **Implementar**.  
  
17. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
18. En la consola de administración de BizTalk, expanda **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)** y, a continuación, expanda **Hosts**.  
  
19. En el panel derecho, haga clic con el botón derecho en el nombre del host y, a continuación, haga clic en **Detener**. Una vez detenido el servicio, haga clic con el botón derecho en el nombre del host y, a continuación, haga clic en **Iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [Incorporación de un nuevo proceso de interfaz de socio comercial](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)