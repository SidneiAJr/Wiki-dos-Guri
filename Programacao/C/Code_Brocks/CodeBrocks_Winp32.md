# Tutorial de criação Tela com WinAPI32 

- Tela de Seleção do CodeBlocks:

![Botão](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-29%20194122.png)

- Tela Para Verificar Form ou Dialog:

![Dialogue](https://github.com/SidneiAJr/Documentacao/blob/main/prints/b.png)


Este tutorial ensina passo a passo como criar uma **janela simples no Windows** usando a **API Win32 (C)** no **Code::Blocks com MinGW**.

---

## 🎯 Objetivo
Criar uma janela Win32 básica com tratamento de mensagens e um botão funcional, compilando no **Code::Blocks**.

---

## 🧰 Pré-requisitos
- **Sistema operacional:** Windows  
- **IDE:** [Code::Blocks](https://www.codeblocks.org/) com **MinGW**  
- **Linguagem:** C  
- Conhecimento básico sobre estruturas e ponteiros  

---

## 🧩 Estrutura mínima de um programa Win32
Um app Win32 precisa de:
- Uma **classe de janela** (`WNDCLASSEX`)
- Função **WndProc** (Window Procedure)
- Função principal **WinMain**
- **Loop de mensagens** (`GetMessage`, `DispatchMessage`)
- Chamada a **CreateWindowEx**, **ShowWindow**, e **UpdateWindow**

---

## 💻 Código completo (`main.c`)

```c
#include <windows.h>

const char g_szClassName[] = "MeuAppWin32";

// Prototipo da Window Procedure
LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

// Função principal (subsystem: Windows)
int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance,
                   LPSTR lpCmdLine, int nCmdShow)
{
    WNDCLASSEX wc = {0};
    HWND hwnd;
    MSG Msg;

    wc.cbSize = sizeof(WNDCLASSEX);
    wc.style = CS_HREDRAW | CS_VREDRAW;
    wc.lpfnWndProc = WndProc;
    wc.hInstance = hInstance;
    wc.hIcon = LoadIcon(NULL, IDI_APPLICATION);
    wc.hCursor = LoadCursor(NULL, IDC_ARROW);
    wc.hbrBackground = (HBRUSH)(COLOR_WINDOW + 1);
    wc.lpszClassName = g_szClassName;

    if (!RegisterClassEx(&wc)) {
        MessageBox(NULL, "Falha ao registrar a classe da janela!", "Erro", MB_ICONERROR | MB_OK);
        return 0;
    }

    hwnd = CreateWindowEx(
        0,
        g_szClassName,
        "Minha Janela Win32 (Code::Blocks)",
        WS_OVERLAPPEDWINDOW,
        CW_USEDEFAULT, CW_USEDEFAULT, 800, 600,
        NULL, NULL, hInstance, NULL);

    if (!hwnd) {
        MessageBox(NULL, "Falha ao criar a janela!", "Erro", MB_ICONERROR | MB_OK);
        return 0;
    }

    ShowWindow(hwnd, nCmdShow);
    UpdateWindow(hwnd);

    while (GetMessage(&Msg, NULL, 0, 0) > 0) {
        TranslateMessage(&Msg);
        DispatchMessage(&Msg);
    }

    return (int)Msg.wParam;
}
```
```c
// Window Procedure
LRESULT CALLBACK WndProc(HWND hwnd, UINT msg, WPARAM wParam, LPARAM lParam)
{
    switch (msg)
    {
    case WM_PAINT: {
        PAINTSTRUCT ps;
        HDC hdc = BeginPaint(hwnd, &ps);
        TextOut(hdc, 10, 10, "Olá, Win32!", 11);
        EndPaint(hwnd, &ps);
        break;
    }

    case WM_DESTROY:
        PostQuitMessage(0);
        break;

    default:
        return DefWindowProc(hwnd, msg, wParam, lParam);
    }
    return 0;
}
```
## 3. Compilar e executar

Pressione F9 ou Build → Run.
Uma janela deve aparecer com o texto “Olá, Win32!”.

| Seção                         | Descrição                                  |
| ----------------------------- | ------------------------------------------ |
| `WNDCLASSEX`                  | Define os atributos da classe da janela    |
| `RegisterClassEx`             | Registra a classe para uso                 |
| `CreateWindowEx`              | Cria uma instância da janela               |
| `ShowWindow` / `UpdateWindow` | Exibe e atualiza a janela                  |
| `GetMessage` loop             | Mantém o programa executando até `WM_QUIT` |
| `WndProc`                     | Lida com eventos (mensagens do sistema)    |
| `WM_PAINT`                    | Evento de redesenho da janela              |
| `WM_DESTROY`                  | Quando a janela é fechada                  |



