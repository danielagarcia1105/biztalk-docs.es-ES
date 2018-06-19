---
title: 'Paso 8: Crear e implementar la orquestación de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209308"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a>Paso 8: Crear e implementar la orquestación de Contoso
En este paso, compilará el proyecto de orquestación y lo implementará mediante el Asistente para la implementación de BizTalk. Esto agrega el ensamblado a la base de datos de configuración e instala el ensamblado en la caché global de ensamblados (GAC).  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>Para asignar un nombre seguro al ensamblado  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PrivateResponder** y, después, haga clic en **Propiedades**.  
  
2.  En el cuadro de diálogo Páginas de propiedades de PrivateResponder, seleccione **Ensamblado** en el panel izquierdo.  
  
3.  En el panel derecho, desplácese hacia abajo hasta la sección **Nombre seguro** , haga clic en el campo situado a la derecha del **Archivo clave de ensamblado**y, después, haga clic en el botón de puntos suspensivos (**...**).  
  
4.  Busque la carpeta del proyecto, seleccione el archivo **FabConPriceAvail.snk** y, después, haga clic en **Abiertos**.  
  
5.  En el panel derecho, seleccione **False** en la lista desplegable **Signo de retraso de ensamblado** .  
  
6.  Haga clic en **Aceptar** para guardar los cambios.  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a>Para compilar e implementar el proyecto de orquestación  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **PrivateResponder** y, después, haga clic en **Compilar**.  
  
    > [!NOTE]
    >  Puede omitir las advertencias que se producen durante el proceso de compilación.  
  
2.  Después de finalizar la compilación, vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, haga clic en **Implementar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 9: Iniciar la orquestación de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)