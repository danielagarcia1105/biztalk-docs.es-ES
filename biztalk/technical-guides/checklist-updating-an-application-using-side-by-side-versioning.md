---
title: "Lista de comprobación: Actualizar una aplicación mediante las versiones de Side-by-Side | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3adee8da-18d4-4b9e-a22e-148b90d18179
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5447743ff9cdc7a109d78c3dac57e0e3345556a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-application-using-side-by-side-versioning"></a>Lista de comprobación: Actualizar una aplicación mediante las versiones en paralelo
La siguiente lista de comprobación describe el proceso de implementación de una versión actualizada de una aplicación de BizTalk que se ejecutará en paralelo con una versión existente.  
  
 Una instalación en paralelo puede desplegar una actualización de la aplicación de forma incremental. Hacer que la instalación disponible para un subconjunto de los socios comerciales inicialmente, en lugar de a todos los asociados a la vez. Con este enfoque permite continuar ejecutando la aplicación existente para los usuarios que aún no están usando la nueva versión hasta que esté listo para migrar completamente a la nueva versión del servicio.  
  
 Las dos aplicaciones side-by-side tendrá que recibir mensajes en diferentes ubicaciones de recepción. Como resultado, para ejecutar aplicaciones en paralelo debe pedir a esos socios comerciales que debe usar la nueva versión de la aplicación para enviar mensajes a la nueva ubicación de recepción, para que sean procesados por la nueva versión. Los socios comerciales que deben usar la versión anterior deben enviar mensajes a la anterior ubicación de recepción.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Cree e implemente una estrategia de control de versiones.|Sección "Control de versiones" [prácticas recomendadas para actualizar aplicaciones](../technical-guides/best-practices-for-updating-applications.md).|  
|Realice los cambios necesarios para los proyectos que se van a implementar en la nueva versión de la aplicación.|-   [Cómo crear o agregar un artefacto](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724).<br />-   [Administrar artefactos](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725).<br />-   [Archivos de enlace e implementación de la aplicación](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).<br />-   [Agregar artefactos a una aplicación](../technical-guides/adding-artifacts-to-an-application.md)|  
|Incrementar el número de versión de cada ensamblado.|[Cómo actualizar un ensamblado](../technical-guides/how-to-update-an-assembly.md)|  
|Establecer las propiedades de implementación para cada proyecto de la solución (configuración de la aplicación de destino y habilitar la instalación en la caché de ensamblados global (GAC)).|[Cómo actualizar un ensamblado](../technical-guides/how-to-update-an-assembly.md)|  
|Implementar soluciones que contienen los ensamblados que hayan cambiado en una aplicación en el entorno de desarrollo.|-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).<br />-   [Cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720).<br />-   [Implementar un ensamblado](../technical-guides/deploying-an-assembly.md)|  
|Crear un nuevo puerto de recepción y cualquier ubicaciones de recepción necesarias especificando las nuevas direcciones URL que desee que los socios para enviar los mensajes.<br /><br /> Cree los puertos de envío adecuado según sea necesario.<br /><br /> Si es necesario, puertos de enlace la nueva aplicación en recién creada de recepción y envío y compruebe que la aplicación funciona:|-   [Cómo crear un puerto de recepción](http://go.microsoft.com/fwlink/?LinkId=154843) (http://go.microsoft.com/fwlink/?LinkId=154843).<br />-   [Cómo crear una ubicación de recepción](http://go.microsoft.com/fwlink/?LinkId=154844) (http://go.microsoft.com/fwlink/?LinkId=154844).<br />-   [Cómo crear un puerto de envío](http://go.microsoft.com/fwlink/?LinkId=154845) (http://go.microsoft.com/fwlink/?LinkId=154845).<br />-   [Cómo configurar una aplicación](http://go.microsoft.com/fwlink/?LinkId=154847) (http://go.microsoft.com/fwlink/?LinkId=154847).|  
|Exportar la nueva aplicación en un archivo .msi desde el entorno de desarrollo.|-   [Cómo exportar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154848) (http://go.microsoft.com/fwlink/?LinkId=154848).<br />-   [Archivos de enlace e implementación de la aplicación](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).<br />-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)|  
|Importar el archivo .msi de aplicación en el grupo de BizTalk en el entorno de producción.|-   [Cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154827) (http://go.microsoft.com/fwlink/?LinkId=154827).<br />-   [Cómo instalar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154728) (http://go.microsoft.com/fwlink/?LinkID=154728).<br />-   [Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-   [Cómo importar enlaces desde un archivo de enlace](../technical-guides/how-to-import-bindings-from-a-binding-file.md)|  
|Realizar un inicio completo de la aplicación.|-   [Cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154729) (http://go.microsoft.com/fwlink/?LinkID=154729).<br />-   [Tareas de prueba para la implementación de aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154825) (http://go.microsoft.com/fwlink/?LinkId=154825).|  
|Notifique a los socios que debería empezar a enviar mensajes a las nuevas direcciones URL. Cuando lo hagan, la aplicación comenzará a procesar los mensajes de los socios especificados.|-|