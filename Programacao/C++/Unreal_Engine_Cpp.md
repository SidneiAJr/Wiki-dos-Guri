# 🎮 Introdução ao Unreal Engine com C++

## 🎯 Objetivo
Aprender como o **C++ é usado dentro da Unreal Engine**, a engine responsável por diversos jogos AAA, simuladores e produções cinematográficas.

---

## 🧱 Estrutura Básica da Unreal Engine
Um projeto Unreal se organiza em classes e objetos específicos do motor:

| Classe | Função Principal |
|---------|------------------|
| `AActor` | Base para qualquer objeto do jogo que pode ser colocado em cena. |
| `APawn` | Entidade controlável por jogador ou IA. |
| `ACharacter` | Subclasse de `Pawn` com movimentação e animações prontas. |
| `UComponent` | Comportamentos anexáveis a objetos (ex: câmera, colisão). |
| `UWorld` | Gerencia todos os objetos, cenas e níveis do jogo. |

---

## 🧩 Exemplo — Classe de Personagem

```cpp
#include "GameFramework/Character.h"
#include "MyCharacter.generated.h"

UCLASS()
class AMyCharacter : public ACharacter
{
    GENERATED_BODY()

public:
    AMyCharacter();

protected:
    virtual void BeginPlay() override;

public:
    virtual void Tick(float DeltaTime) override;
    virtual void SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent) override;

private:
    void MoveForward(float Value);
    void MoveRight(float Value);
};
#include "MyCharacter.h"
#include "GameFramework/Controller.h"
#include "GameFramework/SpringArmComponent.h"
#include "Camera/CameraComponent.h"

AMyCharacter::AMyCharacter()
{
    PrimaryActorTick.bCanEverTick = true;
}

void AMyCharacter::BeginPlay()
{
    Super::BeginPlay();
}

void AMyCharacter::Tick(float DeltaTime)
{
    Super::Tick(DeltaTime);
}

void AMyCharacter::SetupPlayerInputComponent(UInputComponent* PlayerInputComponent)
{
    PlayerInputComponent->BindAxis("MoveForward", this, &AMyCharacter::MoveForward);
    PlayerInputComponent->BindAxis("MoveRight", this, &AMyCharacter::MoveRight);
}

void AMyCharacter::MoveForward(float Value)
{
    AddMovementInput(GetActorForwardVector() * Value);
}

void AMyCharacter::MoveRight(float Value)
{
    AddMovementInput(GetActorRightVector() * Value);
}
```
