# �X�֔ԍ����ܓx�o�x�����̏o���� �R�}���h

[jq](http://stedolan.github.io/jq/)��[xmllint](http://xmlsoft.org/xmllint.html)�Ƃ������R�}���h�̎g�����肪�Ȃ��Ă����̂ŁA[�Ǝ�JSON&XML��̓R�}���h](https://github.com/ShellShoccar-jpn/Parsrs)�ƁA���̉��p�i�ł��邱�̃R�}���h�g**getsunrise.sh**�h��������B�ǂ����Ȃ��Ă����̂���[Qiita](http://qiita.com/)��ɋL��������[�Z�N�V����](http://qiita.com/richmikan@github/items/e051b5d882c3dd2a39c6#jq%E3%82%84xmllint%E7%AD%89%E3%81%AFunix%E5%93%B2%E5%AD%A6%E3%81%AB%E6%9F%93%E3%81%BE%E3%82%8A%E3%81%8D%E3%81%A3%E3%81%A6%E3%81%84%E3%81%AA%E3%81%84)�ł����Ă菑�����̂œǂ�ł��邪�悢�B

�܂��Ƃɂ����A�����ł͂���getsunrise���g���Ă݂�B

## �C���X�g�[�����@

[curl](http://curl.haxx.se/)��[wget](http://www.gnu.org/software/wget/)�������Ă���UNIX���Ȃ�قƂ�ǂ̊��œ����B������� **jq�Ƃ�xmllint�Ƃ��s�v�BJSON��XML�̉�͂�sed��AWK�ōς܂��Ă���B

����āA��L�̂ǂ��炩���C���X�g�[��������A���̂悤�ɂ��Ă��̃��|�W�g���[��git clone����Ί������B

```sh:�C���X�g�[�����@
$ git clone https://github.com/ShellShoccar-jpn/getsunrise.git
```

�������Agit���C���X�g�[������Ă����Ə�L�̃R�}���h�͎g����ȁBgit�������Ƃ�unzip�R�}���h������Ȃ�
> [https://github.com/ShellShoccar-jpn/getsunrise/archive/master.zip](https://github.com/ShellShoccar-jpn/getsunrise/archive/master.zip)

����t�@�C�����_�E�����[�h�A�W�J�A����README.md�ȊO�̂��ׂẴt�@�C���Ɏ��s�p�[�~�b�V�����Z�b�g�Ŏg����悤�ɂȂ邼�B

## �g����

�R�}���h�̈����ɗX�֔ԍ��i`nnn-nnnn`�j��t����΂悢�������B

```bash:���s��
$ ./getsunrise.sh 288-0012 2014/01/01
��t�����q�s���i��A20140101�̓��̏o�E���̓������𒲂ׂ܂��B
(15�b���炢�҂��Ă�...)

��t�����q�s���i��(�ܓx=35.706987,�o�x=140.861803)�ɂ�����A
2014�N1��1���� ���̏o������6:46�A���̓�������16:34�A�݂����ł���B
$ ./getsunrise.sh 100-2100 2014/01/01 # �����{�ꑁ�������̏o�̎����́H
#(���ۂɓ������Ă݂Ă�������)
$ 
```

���ʂ��o��܂�15�b���炢�҂�����邪�A�����API�̎d�l���B��X�̃V�F���X�N���v�g�̂����ł͂Ȃ����I

## �Z�p���

���̃R�}���h������Ă��鎖�͉��L�̂Ƃ��肾�B�v�����WebAPI��n������Ă���̂��B

1. �R�}���h��������X�֔ԍ����󂯎��B
2. [�X�֔ԍ�����WebAPI](http://geoapi.heartrails.com/)�Ɋ|���āA�n���ƈܓx�E�o�x�𓾂�B
3. ����ɁA[���̏o�E���̓�����WebAPI](http://labs.bitmeister.jp/ohakon/index.cgi)�Ɋ|���āA���̏o�E���̓��莞���𓾂�B

�\�[�X�R�[�h�ɋ���������҂́A���̃��|�W�g���[�̒��g���������茩�܂킷���悢�B[getsunrise.sh](https://github.com/ShellShoccar-jpn/getsunrise/blob/master/getsunrise.sh)�{�̂ȂǁA�R�����g���s�������΂�������85�s�̃V�F���X�N���v�g���B
