<style scoped>
    *{
        margin: 0;
        padding: 0;
    }

    .section{
        height: 700px;
        background: #D3D3D3;
        display: flex;
        justify-content: center;
        align-items: center;
        background: url("https://quwi.com/img/backgrounds/gray_blur.png");
    }

    .modal{
        max-width: 360px;
        width: 100%;
        padding: 25px 40px 35px;
        background: #fff;
        border: 1px solid rgba(0,0,0,.11);
        box-shadow: 0 0 12px rgb(0 0 0 / 25%);
        border-radius: 15px;
        margin: 0 10%;
    } 

    .title{
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 14px;
        font-family: Arial,sans-serif;
        font-weight: 700;
        font-size: 24px;
        margin-bottom: 26px;
    }

    .inputField{
        position: relative;
        padding: 15px 0;
        max-width: 360px;
        width: 100%;
        height: 100%;
        border: 1px solid #dadada;
        border-radius: 5px;
        outline: none;
        font-size: inherit;
        margin-bottom: 12px;
        text-align: calc(100% - 10px);
    }

    input{
        width: 90%;
        border: none;
        outline: none;
        padding: 0 15px;
    }
    
    .inputTitle{
        font-family: Arial,sans-serif;
        font-size: 14px;
        color: #999;
        position: absolute;
        background: white;
        padding: 0 2px;
        top: -9px;
        left: 12px
    }

    .emailEmpty {
        display: none;
    }

    .passwordEmpty{
        display: none;
    }

    .inputSection button{
        background: #2668c1;
        height: 52px;
        width: 100%;
        font-size: 18px;
        border-radius: 9px;
        font-weight: 400;
        margin-top: 17px;
        margin-bottom: 20px;
        outline: none;
        border: none;
        color: #fff;
        font-family: Arial;
        font-style: normal;
        line-height: 14px;
        cursor: pointer;
    }

    .inputSection button:hover{
        opacity: 0.7;
    }

    .forgotPass{
        color: #2975dc;
        font-family: Arial,sans-serif;
        font-size: 14px;
        word-spacing: 1px;
        text-align: center;
        cursor: pointer;
    }

    .forgotPass:hover{
        text-decoration: underline;
    }
</style>