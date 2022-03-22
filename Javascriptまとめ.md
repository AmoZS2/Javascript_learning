### �ϐ��Ɛ錾
- const
���đ���ł��Ȃ��ϐ��i�萔�Ƃ͌���Ȃ��j
- let
���ϐ��A�����l���w�肵�Ȃ��ϐ�����`�ł���iundefined�ɂȂ�j
- var
��let�Ǝ��Ă��邪�A�萔���đ���ł��Ă��܂�

### �f�[�^�^�ƃ��e����
- �e���v���[�g���e����
�u``�v
���낢����H�ł��镶����

### ���Z�q
- NaN(Not-a-Number)�͐��l�łȂ�Number�^��\��
Number.isNaN�Ŕ���ł���
- �������
���ڂ������L
- Nullish coalescing���Z�q�i??�j
���ӂ�nullish���ǂ����Œl�����߂�
���̒l�����邩������Ȃ��Ƃ��Ɏg��
```javascript
console.log(undefined ?? "�E�ӂ̒l"); // => "�E�ӂ̒l"
```

### �ÖٓI�Ȍ^�ϊ�
- Symbol(" ")�͈ÖٓI�Ɍ^�ϊ��ł��Ȃ�
�����I�ł����ϊ��ł��Ȃ��悤�ɂ������Ƃ��Ɏg���H

### �֐��Ɛ錾
- �f�t�H���g����
??�ł���p�\
```javascript
function echo(x = "�f�t�H���g�l") {
    return x;
}

console.log(echo(1)); // => 1
console.log(echo()); // => "�f�t�H���g�l"
```

- Rest parameters
�������̐擪�Ɂu...�v������������
�z��Ƃ��đ�������
���̈����Ƒg�ݍ��킹��Ƃ��͖�����
�u...array�v�������ɓn���Ɗ֐����ɓW�J�ł���
```javascript
function fn(arg1, ...restArgs) {
    console.log(arg1); // => "a"
    console.log(restArgs); // => ["b", "c"]
}
fn("a", "b", "c");
```
- spread�\��
�z��̑O��...�������\��

- Arrow Function
```javascript
// Arrow Function���g�����֐���`
const �֐��� = () => {
    // �֐����Ăяo�����Ƃ��̏���
    // ...
    return �֐��̕Ԃ��l;
};
```

- ���\�b�h�̒Z�k�L�@
```javascript
const obj = {
    method() {
        return "this is method";
    }
};
console.log(obj.method()); // => "this is method"
```

### ���[�v�Ɣ�������
- some���\�b�h
�z��̊e�v�f���e�X�g����֐����󂯎��
```javascript
function isEven(num) {
    return num % 2 === 0;
}
const numbers = [1, 5, 10, 15, 20];
console.log(numbers.some(isEven)); // => true
```

- filter���\�b�h
�z��̓���̒l�ŐV�����z����쐬
```javascript
function isEven(num) {
    return num % 2 === 0;
}

const array = [1, 5, 10, 15, 20];
console.log(array.filter(isEven)); // => [10, 20]
```

### �I�u�W�F�N�g
- �v���p�e�B���ƒl�������ꍇ�̏ȗ��L�@
{name}�̂悤�ɂȂ��Ă������
- �I�u�W�F�N�g�̃A�N�Z�X���@
�h�b�g�L�@�i.�j�ƃu���P�b�g�L�@�i['']�j������
�v���p�e�B���ɕϐ����w�肵�����ꍇ�Ȃǂ̓u���P�b�g�L�@���g��
- �I�u�W�F�N�g�̕������
���W���[����import�Ƃ��ɏo�Ă���
```javascript
const languages = {
    ja: "���{��",
    en: "�p��"
};
const { ja, en } = languages;
console.log(ja); // => "���{��"
console.log(en); // => "�p��"
```
- Optional chaining���Z�q(?.)
���ӂ�nullish(null �� undefined)�Ȃ�undefined��Ԃ�
```javascript
const obj = {
    a: {
        b: "obj��a�v���p�e�B��b�v���p�e�B"
    }
};
// obj.a.b �͑��݂���̂ŁA���̕]�����ʂ�Ԃ�
console.log(obj?.a?.b); // => "obj��a�v���p�e�B��b�v���p�e�B"
// ���݂��Ȃ��v���p�e�B�̃l�X�g��`undefined`��Ԃ�
// �h�b�g�L�@�̏ꍇ�͗�O���������Ă��܂�
console.log(obj?.notFound?.notFound); // => undefined
// undefined��null��nullish�Ȃ̂ŁA`undefined`��Ԃ�
console.log(undefined?.notFound?.notFound); // => undefined
console.log(null?.notFound?.notFound); // => undefined
```
- �ÓI���\�b�h�{�z���forEach�Ȃǂ�g�ݍ��킹��ƃv���p�e�B�ɔ��������ł���
```javascript
const obj = {
    "one": 1,
    "two": 2,
    "three": 3
};
const keys = Object.keys(obj);
keys.forEach(key => {
    console.log(key);
});
// ���̒l�����Ԃɏo�͂����
// "one"
// "two"
// "three"
```
- �I�u�W�F�N�g��spread�\���i...�j���v���p�e�B���Ɏw��ł���

### �z��
- Array.prototype.at
array.at(-1)�ōŌ�̒l���w��ł���

- Spread�\���Ŕz��̔C�ӂ̏ꏊ�ɔz���W�J�ł���
- ���\�b�h�`�F�[���ƍ��K�֐�
�L�q���Ȍ��ɂł���

### ������
- ���K�\���AURL�A�p�X�ȂǓ����I�ȕ��삪�܂܂��

### �������Unicode
- Code Unit��G�����������ꍇ�ɂ��ď�����Ă���

### �֐���this
- �l�X�Ȋ֐��̏��������ڂ��Ă���
- ���\�b�h��this���g��
- call�Aapply�Abind

### �N���X
�H�H