<style scoped>
    .openModal{
        max-width: 100%;
        width: 100%;
        display: flex;
        justify-content: center;
        position: absolute;
        top: 15%;
        animation-name: modalAnimation;
        animation-duration: 1s;
        z-index: 3;
    }

    .closeModal{
        max-width: 100%;
        width: 100%;
        display: flex;
        justify-content: center;
        position: absolute;
        top: 15%;
        animation-name: modalAnimation;
        animation-duration: 2s;
        z-index: 3;
        display: none;
    }

    .isClose{
        display: none
    }

    @keyframes modalAnimation {
        from {top: 0;}
        to {top: 15%;}
    }

    .newName{
        display: flex;
        align-items: center;
        flex-direction: column;
        width: 50%;
        padding: 50px 35px;
        background: #fff;
        border: 1px solid rgba(0,0,0,.11);
        box-shadow: 0 0 12px rgb(0 0 0 / 25%);
        border-radius: 15px;
    }

    .newName input{
        border: 2px solid red;
        padding: 15px;
        font-size: 18px;
        border: 1px solid rgba(0,0,0,.11);
        box-shadow: 0 0 12px rgb(0 0 0 / 25%);
        border-radius: 5px;
    }

    .newName button {
        height: 40px;
        width: 50%;
        font-size: 18px;
        border-radius: 9px;
        font-weight: 400;
        outline: none;
        border: none;
        color: #fff;
        font-family: Arial, Helvetica, sans-serif;
        font-style: normal;
        line-height: 14px;
        cursor: pointer;
        min-width: 150px
    }

    .submitBtn{
        background: #2668c1;
        margin-top: 35px;
    }

    .cancelBtn{
        background: #A9A9A9;
        margin-top: 12px;

    }

    .newName button:hover {
        opacity: 0.7;
    }
</style>