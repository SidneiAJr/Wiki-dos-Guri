# Tutorial TypeScript - Simulador de Tanques

```ts
// Interface que define os métodos obrigatórios para qualquer tanque
interface VerificarVida {
    VerificarCalibre(): void;                  // Verifica efeito do calibre
    VerificarArmadura(): void;                 // Verifica efeito da blindagem
    PaisTank(): void;                           // Mostra país do tanque
    TierTank(): void;                           // Mostra tier do tanque
    Atacar(aliado: Tank): void;                // Método de ataque a outro tanque
    Falas(): void;                              // Mensagens de aviso do tanque
    Artilharia(): void;                         // Uso de artilharia
    Inimigo(aliado: Tank): void;               // Ações do inimigo contra aliado
}

// Classe abstrata que implementa VerificarVida
abstract class TankStatus implements VerificarVida {
    constructor(
        public NomeTank: string,
        public calibre: number,
        public blindagem: number,
        public municao: number,
        public vidaMax: number,
        public dano: number,
        public penetracaoMunicao: number,
        public TipoMunicao: string,
        public tierTank: number,
        public paisTank: string,
        public blindagemSTatus: boolean
    ) {}

    // Métodos vazios que serão implementados na classe concreta
    VerificarArmadura(): void {}
    VerificarCalibre(): void {}
    Verificarmunicao(): void {}
    VerificarVida(): void {}
    PaisTank(): void {}
    TierTank(): void {}
    Atacar(aliado: Tank): void {}
    Artilharia(): void {}
    Falas(): void {}
    Inimigo(aliado: Tank): void {}
}

// Classe concreta que representa um tanque
class Tank extends TankStatus implements VerificarVida {
    
    // Verifica a blindagem do tanque e mostra chance de penetração
    VerificarArmadura(): void {
        if (this.blindagem <= 50) {
            console.log(`Chance de Penetração 75%`);
        } else if (this.blindagem <= 25) {
            console.log(`Chance de Penetração 25%`);
        } else {
            console.log(`Chance de Penetração 0%`);
        }
    }

    // Verifica calibre da arma e aplica dano/vida
    VerificarCalibre(): void {
        if (this.calibre <= 88) {
            this.dano += 90;
            this.vidaMax -= 20;
            console.log(`${this.NomeTank} atingiu e causou dano! Vida: ${this.vidaMax}, Dano: ${this.dano}, Calibre: ${this.calibre}`);
        } else if (this.calibre <= 128) {
            this.dano += 190;
            this.vidaMax -= 100;
            console.log(`Dano causado: ${this.dano}, Vida perdida: ${this.vidaMax}, Calibre: ${this.calibre}`);
        } else {
            this.dano += 20;
            this.vidaMax -= 20;
            console.log(`Dano causado: ${this.dano}, Vida perdida: ${this.vidaMax}, Calibre: ${this.calibre}`);
        }
    }

    // Verifica e reduz munição, mostrando tipo selecionado
    Verificarmunicao(): void {
        this.municao -= 1;
        console.log(`Munição restante: ${this.municao}`);

        switch (this.TipoMunicao) {
            case "AP":
                console.log("Municao Selecionada: AP");
                break;
            case "HE":
                console.log("Municao Selecionada: HE");
                break;
            case "APHEBC":
                console.log("Municao Selecionada: APHEBC");
                break;
            case "APDS":
                console.log("Municao Selecionada: APDS");
                break;
            default:
                console.log("Selecione a munição correta");
                break;
        }
    }

    // Verifica vida máxima
    VerificarVida(): void {
        if (this.vidaMax < 100) {
            this.vidaMax = 100;
            console.log(`Vida Máxima ajustada: ${this.vidaMax}`);
        } else {
            console.log(`Vida Máxima: ${this.vidaMax}`);
        }
    }

    // Mostra tier do tanque
    TierTank(): void {
        console.log(`Tier do Tank: ${this.tierTank}`);
    }

    // Mostra país do tanque
    PaisTank(): void {
        // <- Lógica do if está incorreta (sempre retorna true)
        if (this.paisTank=="Alemanha"|| "Reino Unido"|| "USA"|| "Franca"|| "ITA") {
            console.log(`País do Tank: ${this.paisTank}`);
        } else {
            console.log(`Árvore em construção!`);
        }
    }

    // Ataca outro tanque aliado
    Atacar(aliado: Tank): void {
        if (this.penetracaoMunicao >= aliado.blindagem) {
            console.log("Ataque bem-sucedido! Módulos inimigos danificados.");
            aliado.vidaMax -= this.dano;
            console.log(`Vida do tanque aliado após ataque: ${aliado.vidaMax}`);
        } else {
            console.log(`Blindagem do inimigo (${aliado.blindagem}mm) maior que penetração (${this.penetracaoMunicao}mm). Ataque falhou.`);
        }
    }

    // Mostra artilharia disponível dependendo do tempo e vida
    Artilharia(): void {
        const tempopartida = 500;
        if (tempopartida >= 500 || this.vidaMax <= 50) {
            console.log("Artilharia disponível");
        } else if (tempopartida >= 1000 || this.vidaMax <= 25) {
            console.log("Aviso! Artilharia Nuclear disponível");
        }
    }

    // Mensagens do tanque dependendo da blindagem
    Falas(): void {
        if (this.blindagemSTatus) {
            console.log("Aviso! Fomos atingidos sem dano");
        } else {
            console.log("Aviso! Blindagem penetrada!");
        }
    }

    // Lógica de ações do inimigo
    Inimigo(aliado: Tank): void {
        if (this.vidaMax <= 25) {
            console.log("Inimigo em perigo! Tentando aumentar blindagem...");
            this.VerificarArmadura();
        } else if (this.municao > 0 && this.penetracaoMunicao >= aliado.blindagem) {
            console.log("Inimigo ataca com força total!");
            this.Atacar(aliado);
        } else if (this.municao <= 0) {
            console.log("Inimigo sem munição, recarregando!");
            this.Verificarmunicao();
        } else {
            const acao = Math.floor(Math.random() * 3);
            switch (acao) {
                case 0:
                    console.log("Inimigo usa artilharia!");
                    this.Artilharia();
                    break;
                case 1:
                    console.log("Inimigo tenta verificar calibre.");
                    this.VerificarCalibre();
                    break;
                case 2:
                    console.log("Inimigo verifica blindagem.");
                    this.VerificarArmadura();
                    break;
                default:
                    console.log("Inimigo aguardando...");
                    break;
            }
        }
    }
}

// ==============================
// 🚀 TESTES
// ==============================
console.log("======================================= Luta 1 =============================");

const tank1 = new Tank("Tiger II", 88, 600, 10, 100, 100, 100, "AP", 6, "Alemanha", true);
tank1.VerificarArmadura();
tank1.VerificarCalibre();
tank1.VerificarVida();
tank1.Verificarmunicao();
tank1.PaisTank();
tank1.TierTank();
tank1.Atacar(tank1); // <- Aqui deveria atacar outro tanque
tank1.Artilharia();
tank1.Falas();
tank1.Inimigo(tank1); // <- Aqui também deveria ser outro tanque

console.log("======================================= Luta 2 =============================");

const inimigo1 = new Tank("Sherman", 75, 35, 20, 300, 35, 75, "AP", 5, "USA", true);
inimigo1.VerificarArmadura();
inimigo1.VerificarCalibre();
inimigo1.VerificarVida();
inimigo1.Verificarmunicao();
inimigo1.PaisTank();
inimigo1.TierTank();
inimigo1.Atacar(tank1);
inimigo1.Artilharia();
inimigo1.Falas();
inimigo1.Inimigo(tank1);

console.log("======================================= Luta 3 =============================");

const tank2 = new Tank("Jagtiger", 128, 600, 10, 100, 100, 100, "AP", 6.6, "Alemanha", true);
tank2.VerificarArmadura();
tank2.VerificarCalibre();
tank2.VerificarVida();
tank2.Verificarmunicao();
tank2.PaisTank();
tank2.TierTank();
tank2.Atacar(tank1);
tank2.Artilharia();
tank2.Falas();
tank2.Inimigo(tank1);

console.log("======================================= Luta 4 =============================");

const inimigo2 = new Tank("Sherman Firefly", 76.2, 35, 20, 450, 35, 75, "APDS", 5, "Reino Unido", true);
inimigo2.VerificarArmadura();
inimigo2.VerificarCalibre();
inimigo2.VerificarVida();
inimigo2.Verificarmunicao();
inimigo2.PaisTank();
inimigo2.TierTank();
inimigo2.Atacar(tank1);
inimigo2.Artilharia();
inimigo2.Falas();
inimigo2.Inimigo(tank1);

console.log("======================================= Fim =============================");
