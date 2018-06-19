---
title: Agregar certificados al almacén de certificados en el cliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 9e2722ee-dd6f-4b14-9796-2f2157e8cad2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a2e01fa60eccc8a6a0f06f4cf1f9fafb3f982b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209500"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-client"></a>Agregar certificados al almacén de certificados en el cliente
Siga estos pasos para agregar certificados a la carpeta Personal en el almacén de certificados en cada equipo cliente. Los certificados deben agregarse a la carpeta Personal de los certificados: almacén del usuario actual.  
  
> [!IMPORTANT]
>  Si los certificados no se distribuyen a través de una empresa entidad emisora de certificados de confianza, debe importar el certificado de raíz de la entidad de certificación en los equipos cliente. En caso contrario, los certificados personales no funcionará. Importar el certificado de la entidad de certificación en la carpeta entidades emisoras raíz de confianza en el nodo certificados (equipo Local).  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>Para agregar certificados al almacén de certificados  
  
1.  Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. Escriba **mmc**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el cuadro de diálogo Consola1, haga clic en **archivo**y, a continuación, haga clic en **agregar o quitar complemento**.  
  
3.  En el cuadro de diálogo Agregar o quitar complemento, haga clic en **agregar**.  
  
4.  En el cuadro de diálogo Add Standalone Snap-in, haga clic en **certificados**y, a continuación, haga clic en **agregar**.  
  
5.  En el cuadro de diálogo del complemento de certificados, haga clic en **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**.  
  
6.  En el cuadro de diálogo Add Standalone Snap-in, haga clic en **certificados**y, a continuación, haga clic en **agregar**.  
  
7.  En el cuadro de diálogo del complemento de certificados, haga clic en **cuenta de equipo**y, a continuación, haga clic en **siguiente**.  
  
8.  En el cuadro de diálogo Seleccionar equipo, asegúrese de que **equipo Local** está seleccionada y, a continuación, haga clic en **finalizar**.  
  
9. En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.  
  
10. En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.  
  
11. En el **raíz de consola** panel del cuadro de diálogo Consola1, expanda el **certificados - usuario actual** carpetas.  
  
12. En **certificados - usuario actual**, expanda **Personal**.  
  
13. Haga clic en **certificados**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.  
  
14. En la página Asistente para la página del Asistente para importación de certificados, haga clic en **siguiente**.  
  
15. En la página archivo para importar, haga clic en **examinar**.  
  
16. En el cuadro de diálogo Abrir, mover a la ubicación del archivo donde se guardó el certificado, seleccione **todos los archivos** para **archivos es de tipo**, seleccione el certificado que desea importar y, a continuación, haga clic en  **Abra**.  
  
17. En la página archivo para importar, haga clic en **siguiente**.  
  
18. En la página almacén de certificados, compruebe que **colocar todos los certificados en el siguiente almacén** está seleccionado, compruebe que **Personal** se muestra en el **almacén de certificados** cuadro y, a continuación, haga clic en **siguiente**.  
  
19. En la página Finalización la página del Asistente para importación de certificados, haga clic en **finalizar**.  
  
20. En el cuadro de diálogo del Asistente para importar certificados que indica una importación correcta, haga clic en **Aceptar**.  
  
21. Repita los pasos 13 al 20 para todos los demás certificados que se va a utilizar en la reparación de mensajes y nuevo envío.