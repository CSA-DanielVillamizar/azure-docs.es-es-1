---
title: 'Compilación de una aplicación web que llama a las API web: Plataforma de identidad de Microsoft | Azure'
description: Obtenga información sobre cómo compilar una aplicación web que llame a API web (información general)
services: active-directory
author: jmprieur
manager: CelesteDG
ms.service: active-directory
ms.subservice: develop
ms.topic: conceptual
ms.workload: identity
ms.date: 05/07/2019
ms.author: jmprieur
ms.custom: aaddev
ms.openlocfilehash: 5af9e34baf6115e801fbfe35e6e3895e48b360e7
ms.sourcegitcommit: d187fe0143d7dbaf8d775150453bd3c188087411
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80881730"
---
# <a name="scenario-a-web-app-that-calls-web-apis"></a>Escenario: Aplicación web que llama a las API web

Obtenga información sobre cómo compilar una aplicación web que permita iniciar sesión a los usuarios en la Plataforma de identidad de Microsoft y que llame a las API web en nombre del usuario con sesión iniciada.

## <a name="prerequisites"></a>Prerrequisitos

[!INCLUDE [Prerequisites](../../../includes/active-directory-develop-scenarios-prerequisites.md)]

Este escenario supone que ya ha pasado por el escenario siguiente:

> [!div class="nextstepaction"]
> [Aplicación web que permite iniciar sesión a los usuarios](scenario-web-app-sign-user-overview.md)

## <a name="overview"></a>Información general

Agrega autenticación a la aplicación web de manera que permite iniciar sesión a los usuarios y llamar a una API web en nombre del usuario con sesión iniciada.

![Aplicación web que llama a las API web](./media/scenario-webapp/web-app.svg)

Las aplicaciones web que llaman a las API web son aplicaciones cliente confidenciales.
Por este motivo registran un secreto (contraseña de la aplicación o certificado) con Azure Active Directory (Azure AD). Este secreto se pasa durante la llamada a Azure AD para obtener un token.

## <a name="specifics"></a>Características específicas

> [!NOTE]
> Agregar inicio de sesión a una aplicación web consiste en proteger la propia aplicación web. Esa protección se consigue mediante el uso de bibliotecas de *middleware*, no de la biblioteca de autenticación de Microsoft (MSAL). En el escenario anterior, [Aplicación web que permite iniciar sesión a los usuarios](scenario-web-app-sign-user-overview.md), se describió este tema.
>
> En este escenario se explica cómo llamar a las API web desde una aplicación web. Debe obtener tokens de acceso para esas API web. Puede usar las bibliotecas MSAL para adquirir estos tokens.

El desarrollo de este escenario implica estas tareas específicas:

- Durante el [registro de la aplicación](scenario-web-app-call-api-app-registration.md), debe proporcionar un URI de respuesta, un secreto o un certificado que se compartirán con Azure AD. Si implementa la aplicación en varias ubicaciones, proporcionará esta información para cada ubicación.
- La [configuración de la aplicación](scenario-web-app-call-api-app-configuration.md) tiene que proporcionar las credenciales de cliente que se compartieron con Azure AD durante el registro de la aplicación.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Aplicación web que llama a las API web: registro de la aplicación](scenario-web-app-call-api-app-registration.md)
