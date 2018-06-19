---
title: 'Lista de comprobación: Actualizar una orquestación mediante el control de versiones en paralelo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97f66987-0269-4dfe-a648-7b68412e86fe
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8e9ed9f260b7b7b8b269e6a4b5e22411ce05b5c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009941"
---
# <a name="checklist-updating-an-orchestration-using-side-by-side-versioning"></a>Lista de comprobación: Actualizar una orquestación mediante el control de versiones en paralelo
Cambios en las orquestaciones pueden ser más complejas de cambios en otros artefactos, como las asignaciones. Si tiene orquestaciones de corta duración, una actualización simple puede ser suficiente. Pero si tiene orquestaciones de larga ejecución o no se puede finalizar las instancias existentes, control de versiones en paralelo será la única opción.  
  
 Si la orquestación procesa transacciones de larga ejecución, no se puede cambiar a la versión actualizada de la orquestación inmediatamente. Se debe permitir la versión original termine de procesar los mensajes para que no se pierdan. Para ello, implemente la orquestación actualizada en la misma aplicación que la original. A continuación, detenga la versión original e inicie la versión actualizada de modo que reciba todos los mensajes nuevos mientras la versión anterior sigue procesando cualquier mensaje en proceso. Cuando la orquestación original termine de procesar todos los mensajes, anule su implementación desde la aplicación de BizTalk en la que se implementó.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Después de realizar los cambios necesarios en la orquestación, incrementar el número de versión de ensamblado.|[Cómo actualizar un ensamblado](../technical-guides/how-to-update-an-assembly.md)|  
|Implemente el ensamblado desde Visual Studio en una aplicación de BizTalk y, a continuación, pruebe el ensamblado. **Nota:** Asegúrese de seleccionar la opción de implementación para instalar el ensamblado en la GAC.|[Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).|  
|Exporte el ensamblado de la aplicación en el entorno de prueba a un archivo MSI.|[Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)|  
|Importar el archivo .msi en la aplicación de BizTalk en el entorno de producción que contiene la orquestación que desea actualizar. **Nota:** puede usar los pasos siguientes para probar el ensamblado e implementarlo en el entorno de producción.|[Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)|  
|Enlazar la orquestación actualizada usando los mismos enlaces que la orquestación original.|[Cómo configurar enlaces para una orquestación](http://go.microsoft.com/fwlink/?LinkId=154850) (http://go.microsoft.com/fwlink/?LinkId=154850).|  
|Dé de baja la orquestación original y, a continuación, inicie la orquestación actualizada. **Nota:** para evitar que se quiten mensajes, debe hacerlo mediante programación.|Para obtener más información acerca de cómo implementar la orquestación mediante programación, vea [implementar e iniciar una nueva versión de una orquestación mediante programación](http://go.microsoft.com/fwlink/?LinkId=154851) (http://go.microsoft.com/fwlink/?LinkId=154851).<br /><br /> Para obtener más información acerca de cómo implementar la orquestación manualmente, vea lo siguiente en la Ayuda de BizTalk Server:<br /><br /> -   [Cómo dar de baja una orquestación](http://go.microsoft.com/fwlink/?LinkId=154852) (http://go.microsoft.com/fwlink/?LinkId=154852).<br />-   [Cómo dar de alta una orquestación](http://go.microsoft.com/fwlink/?LinkId=154853) (http://go.microsoft.com/fwlink/?LinkId=154853).<br />-   [Cómo iniciar una orquestación](http://go.microsoft.com/fwlink/?LinkId=154854) (http://go.microsoft.com/fwlink/?LinkId=154854).|  
|Supervisar el sistema para instancias de la versión original de orquestación que usan el concentrador de grupo página vista de consulta.|[Cómo ver información de instancia de una orquestación](http://go.microsoft.com/fwlink/?LinkId=154855) (http://go.microsoft.com/fwlink/?LinkId=154855).|  
|Cuando se completa todas las instancias activas, deshidratadas y suspendidas, anular la implementación de la orquestación original de la aplicación.|[Cómo quitar una orquestación de una aplicación](http://go.microsoft.com/fwlink/?LinkId=154856) (http://go.microsoft.com/fwlink/?LinkId=154856).|  
|Si lo desea desinstalar la versión de ensamblado original de la GAC en cada equipo que ejecuta la aplicación.|[Cómo desinstalar un ensamblado de la GAC](http://go.microsoft.com/fwlink/?LinkId=154857) (http://go.microsoft.com/fwlink/?LinkId=154857).|  
  
## <a name="binding-to-receive-ports-and-locations"></a>Enlace de puertos y ubicaciones de recepción  
 Si desea crear nuevos puertos de recepción y ubicaciones para la nueva versión de la orquestación, basta con un enlace a los nuevos puertos y dar de alta o a partir de los artefactos nuevos normalmente será suficientes. Crear nuevas ubicaciones de recepción y puertos suele ser el método preferido, especialmente si su escenario usa orquestaciones de larga duración que recibe un número de poner en correlación todavía necesidad de ser procesados. En este caso, es podrán que no pueda volver a usar existente puertos de recepción o realizar unenlistment. Si crea nuevos puertos, asegúrese de que es posible que los sistemas back-end y de los asociados controlar este cambio. Si no es así, tendrá que esperar culminan antes de actualizar todas las instancias de ejecución prolongada.  
  
 Si desea usar los puertos existentes, realice lo siguiente:  
  
1.  Enlazar la nueva versión de la orquestación a los puertos existentes.  
  
2.  Dar de baja (pero no detiene) la versión anterior de la orquestación.  
  
3.  Dar de alta e iniciar la nueva versión de la orquestación.  
  
    > [!NOTE]  
    >  Puede usar un script para realizar los pasos 2 y 3 en una transacción, para que los mensajes no le faltará suscripciones entre al hacer clic en manual.