---
title: 'Paso 1: Asignar un nombre seguro al ensamblado de Contoso | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d388fc725b8aaeec4cbfa80c23bd5e2a1b42a27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a>Paso 1: Asignar un nombre seguro al ensamblado de Contoso
En este paso, creará y asignará un nombre seguro para el ensamblado de BizTalk. Un nombre seguro garantiza la exclusividad de un ensamblado mediante la asignación de una firma digital y un par de claves exclusivo. Además, un nombre seguro proporciona una comprobación de integridad para garantizar que el contenido del ensamblado no ha cambiado desde que se compiló por última vez.  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a>Para crear un archivo de clave de ensamblado de nombre seguro  
  
1.  Inicie un **símbolo del sistema de Visual Studio 2012**.  
  
2.  En el símbolo del sistema, vaya a la ubicación de la solución de Contoso.  
  
    > [!NOTE]
    >  De forma predeterminada, la ubicación de la solución de Contoso es  *\<unidad\>*: \Documents and Settings\\*\<nombre de usuario\>*\My Documentos\Visual Studio \<versión\>\Projects.  
  
3.  En el símbolo del sistema, escriba **sn -k FabConPriceAvail.sn**y presione **ENTRAR**.  
  
4.  En el símbolo del sistema, escriba **xit**y presione **ENTRAR**.  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>Para asignar un nombre seguro al ensamblado  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **ContosoPriceAndAvailability** y, a continuación, haga clic en **Propiedades**.  
  
2.  En las páginas de propiedades, haga clic en **Firmar** en el panel izquierdo.  
  
3.  En el panel derecho, seleccione **Firmar el ensamblado**.  
  
4.  Haga clic en **Examinar** en el campo Seleccione un archivo de clave de nombre seguro.  
  
5.  Busque la carpeta del proyecto, seleccione el archivo **FabConPriceAvail.snk** que creó anteriormente y, a continuación, haga clic en **Abiertos**.  
  
6.  Haga clic en **Aceptar** para guardar los cambios.  
  
7.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **ContosoPriceAndAvailability** y, a continuación, haga clic en **Compilación**. Después de finalizar la compilación, vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, haga clic en **Implementar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de la consulta/respuesta de disponibilidad](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)