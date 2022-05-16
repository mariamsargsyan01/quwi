<style scoped>
    .projectWrapper {
        display: flex;
        align-items: center;
        padding: 25px;
        border: 1px solid #dedede;
        width: 100%;
        cursor: pointer;
        min-width: 50%;
    }

    .projectWrapper:hover{
       background: #dedede;; 
    }

    .info{
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 65%;

    }

    @media screen and (max-width: 850px) {
        .projectWrapper{
            display: block;
        }

        .info{
            width: 100%;
            margin-bottom: 20px;
            margin-left: 8%;
        }

        .time{
            margin: 0 6%;
        }
    }

    .logo{
        margin-right: 7%;
    }

    .name{
        width: 40%;
        font-family: Arial, Helvetica, sans-serif;
        font-weight: 500;
        font-size: 14px;
    }

    .active{
        width: 30%;
        font-weight: 600;
        font-family: Arial, Helvetica, sans-serif;
    }

    .isActive{
        color: green;
    }

    .isNotActive{
        color: red
    }

    .timeWrapper{
        display: block;
    }
    
    .time{
        display: flex;
        justify-content: space-between;
        gap: 20px;
        font-family: Arial, Helvetica, sans-serif;
        font-size: 14px;
    }
</style>
