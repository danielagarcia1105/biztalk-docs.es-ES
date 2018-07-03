---
title: Administrar lotes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af801bd6ec61c883d81e7ea6fd15e92f2186b777
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021531"
---
# <a name="managing-batches"></a>Administración de lotes
Cómo controlar manualmente el lanzamiento de procesar por lotes los intercambios, con los controles en la parte superior de la **configuración por lotes** página de la ficha de acuerdo unidireccional de la **las propiedades del acuerdo** cuadro de diálogo (en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración) para X12 y la codificación EDIFACT. En estos procedimientos se realizan mediante los siguientes controles:  
  
- **A partir de un lote**. Activa una instancia de la orquestación por lotes. Después de seleccionar el **iniciar** botón, los elementos de procesamiento por lotes se recopilan cuando la instancia está dentro del intervalo de activación.  
  
- **Invalidar un lote**. Crea un lote con los elementos existentes y se envía de inmediato. A continuación, la orquestación de procesamiento por lotes reanuda el procesamiento por lotes según la configuración establecida.  
  
- **Detener un lote**. Desactiva una instancia activada de la orquestación por lotes. Después de seleccionar el **detener** botón, la orquestación crea un lote a partir de elementos de lote existentes, entrega el intercambio a la canalización de envío EDI y finaliza.  
  
  Los controles actúan en una única configuración de lote.  
  
  Las acciones que BizTalk realiza cuando se presiona el **iniciar** botón dependen del **filtro** criterios, **versión** criterios, y **activación**configuración del intervalo en el **configuración por lotes** página. Los criterios de filtro determinan qué mensajes se procesarán por lotes. Los criterios de lanzamiento determinan cuándo se lanzan los lotes. Las propiedades del intervalo de activación determinan si una instancia activada de la orquestación de procesamiento por lotes recopilará elementos para el procesamiento por lotes. Para obtener más información sobre estas opciones, consulte [configurar un lote saliente](../core/configuring-an-outgoing-batch.md).  

Este tema muestra cómo iniciar, detener, reemplazar y eliminar lotes.  

> [!NOTE]
>  Para obtener instrucciones sobre cómo configurar lotes, consulte [configuración X12 procesamiento por lotes](../core/configuring-batching-x12.md) o [configuración de procesamiento por lotes de EDIFACT](../core/configuring-batching-edifact.md). 
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Los miembros del grupo de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueden iniciar, detener o invalidar un lote, pero no pueden cambiar la configuración relativa al procesamiento por lotes. Debe ser miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para cambiar la configuración de lotes.  
  
## <a name="start-stop-and-override-batches"></a>Iniciar, detener o invalidar lotes  
  
1. Abra  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, expanda el grupo de BizTalk y seleccione **partes**.  
  
2. En el **entidades y perfiles empresariales** página, en el **acuerdos** sección, haga clic en el acuerdo con la configuración del lote que desee iniciar, detener o invalidar.  
  
3. En la pestaña del acuerdo unidireccional del **las propiedades del acuerdo**, seleccione el **configuración por lotes** página.  
  
4. En el **configuración por lotes** , seleccione la pestaña del lote que desee iniciar, detener o invalidar.  
  
5. Compruebe que las propiedades de los criterios de filtro, los criterios de lanzamiento y el intervalo de activación son las adecuadas.  
  
   > [!NOTE]
   >  Si es un miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] agrupan operadores, pero no la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo Administradores, puede iniciar, detener o invalidar lotes. Sin embargo, no se puede cambiar la configuración de lotes. Los valores son visibles para usted, pero si cambia una configuración y, a continuación, seleccione **Aceptar**, obtendrá un error de permisos.  
  
6. Si no se ha activado una instancia de la orquestación por lotes, seleccione **iniciar** para activar una instancia.  
  
   > [!NOTE]
   >  - Puede indicar que una instancia de la orquestación por lotes no se ha activado si el **iniciar** botón está habilitado, y **no está activado el procesamiento por lotes** aparece justo debajo del **iniciar** control.  
   >  - Si ha seleccionado la **iniciar** botón y se ha activado una instancia de la orquestación por lotes, pero no se recopilan elementos para el lote, a continuación, compruebe que la fecha y hora en la **activación** ha transcurrido el cuadro de texto. Si no es así, el **activación** debe establecer la fecha en la fecha actual o una versión anterior.  
  
7. Para enviar un intercambio por lotes cuando no se cumplen los criterios de versión, seleccione **invalidar**.  
  
   > [!NOTE]
   >  Seleccionar **invalidar** da como resultado un intercambio por lotes que se envían, pero no afecta al estado de activación de la instancia de orquestación de procesamiento por lotes, los criterios de activación o los criterios de lanzamiento.  
  
8. Para desactivar la instancia de la orquestación por lotes, seleccione **detener**.  
  
   > [!NOTE]
   >  Seleccionar **detener** da como resultado un intercambio por lotes que se envían y la instancia de orquestación de procesamiento por lotes está finalizando.  
  
9. Seleccione **Aceptar** o **cancelar** para cerrar el **las propiedades del acuerdo**.  

## <a name="delete-batches"></a>Eliminar lotes  
  
1. En  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración**, seleccione **partes**.  
  
2. En el **entidades y perfiles empresariales** página, en el **acuerdos** sección, haga clic en el acuerdo con la configuración del lote que desea eliminar.  
  
3. En la pestaña del acuerdo unidireccional del **las propiedades del acuerdo** cuadro de diálogo, seleccione el **configuración por lotes** página.  
  
4. En el **configuración por lotes** , seleccione la pestaña del lote que desea eliminar.  
  
5. En la esquina derecha de la página de ficha, seleccione **eliminar**.  
  
6. Seleccione **Aceptar** para cerrar el **las propiedades del acuerdo**.  

  
## <a name="see-also"></a>Vea también  
 [Configuración de un lote de salida](../core/configuring-an-outgoing-batch.md)  
 [Administrar soluciones EDI y AS2](../core/managing-edi-and-as2-solutions.md)